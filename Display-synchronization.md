Display synchronization techniques
==================================

There seems to be a lot of confusion about the subject of xrandr.lua, fpsadjust.lua, and the new display-sync code. This article should hopefully clear up some of the difference.

The underlying problem
----------------------

First of all, we have to understand what it is they're solving - and here there are multiple separate issues (on both large and small scales) at play. But perhaps the most important underlying problem is the fact that clocks *differ* and *drift*.

Inside a modern PC system there are multiple clock sources that all conflict and interact in various ways (system clock, GPU clock, display refresh rate, audio clock, etc.), and when these disagree with each other or disagree with the specified video and audio timestamps, you run into issues.

For example, suppose (for simplicity) that you're watching a video with 60 Hz video and 48 kHz audio. You can set your audio chip to operate at 48 kHz, and your display is also running at 60 Hz. So in theory it should work out fine if you just let audio play as fast as it wants to, and draw one video frame per monitor refresh, right?

Except in practice, clocks start drifting - so you'd end up with audio/video desynchronization over time if you did that.

Apart from that, there is also the (somewhat separate) issue of clock *mismatch*. For example, suppose your audio hardware can only do 44.1 kHz, but your audio is still 48 kHz - or suppose your video is 24 Hz, but your display only runs at 60 Hz. For audio, the solution (resampling) is uncontroversial and well-known, but for video the situation is more complicated. For that, we have [an entirely separate article](Interpolation.md).

The classic approach
--------------------

Conventionally, mpv (and I believe also VLC, MPlayer, MPC-HC etc.) used this relatively simple design: Just let the (resampled) audio play as fast as it wants (so you get no audio glitches like pops or repeated sections), and if audio/video desynchronization gets too high, then omit or repeat a frame as necessary to keep them synchronized.

This works out fine in practice because dropped or duplicated frames are just barely perceivable as small stutters (unlike audio glitches, which would be much more noticeable pops and clicks), but it still leaves a lot to be desired - especially if you *are* sensitive to video stuttering.

Under the hood, what happens here is that, whenever mpv decides to “show” a new frame, it tells the video output driver to draw this new frame. This happens based on clocks that are entirely independent of the video refresh rate, and essentially mpv's playback loop has zero knowledge of when a vsync actually happens. So it *might* happen that these line up perfectly with the actual vsync timings, but they might also be completely off (and in such cases, frames would get dropped or duplicated). It also complicates other areas of playback, like interpolation, due to there being little correlation between when the VO gets told to draw a frame, and when vsyncs actually happen.

(Note of interest: In the case of playing a video file without any audio, the system clock is used instead of the audio clock - but this mostly works out to be the same because the audio clock tends to be very precise)

Over time, we've come up with multiple ways of improving on or mitigating the issues of this design, most of which are based on the basic principle that audio mismatch is much easier to solve (via resampling) than video mismatch.

fpsadjust.lua
-------------

[This script](https://github.com/haasn/gentoo-conf/blob/nanodesu/home/nand/.mpv/scripts/avail/fpsadjust.lua) tries to mitigate the (relatively common) issue of watching 23.976 Hz video on a monitor that is more compatible with 24.00 Hz (for example 60.00 Hz, 72.00 Hz or 120.00 Hz - in contrast to 59.94 Hz, 71.93 Hz or 119.88 Hz).

This is only a difference of exactly 0.1%, but it was introduced some decades ago due to historical reasons that I won't go into here. The modern upshot is that almost all media is at 23.976 Hz, so unless you have an aforementioned 59.94 Hz (or similar) device, you will run into a 0.1% mismatch between the video timestamps and your display refresh rate, which results in a repeated frame every ``1000 / 60 Hz = 16.6 s``, which can therefore be quite annoying due to how often it occurs.

The solution that fpsadjust.lua uses is to make the video file play slightly faster or slightly slower, via manipulation of the ``--speed`` parameter, in order to compensate for this. So if it sees that you have a 60.0 Hz monitor and are watching a 23.976 Hz clip, it would set ``--speed=1.001`` in order to make the video clip play as if it was 24.000 Hz instead.

(This has the side-effect of making the audio play slightly faster, which requires additional resampling - and may also result in artifacts if using an option like ``--audio-pitch-correction``, which is unfortunately on by default)

Note: Conversely, if you had a 59.95 Hz display and, say, a 30.00 Hz or 60.00 Hz clip (which are relatively common), then this script would set ``--speed=0.999``, thus preventing preventing dropped frames (again every ≈16s).

It's important to note that this is a *static* change only, meaning that it only sets the speed once, at the beginning of playback. This means it's potentially useless for VFR content, or if your video header/container has incorrect or missing FPS tags. (And, in such cases, it might actually make the problem worse.)

xrandr.lua
----------

[This script](https://github.com/lvml/mpv-plugin-xrandr) aims at solving a completely different problem - video/monitor refresh rate incompatibility - by actually changing the rate at which the display updates, which mpv by itself does not touch at all.

For example, if your display is usually 60 Hz but has a 24 Hz mode, and you try playing back a 24 Hz file, then xrandr.lua would set your display to its 24 Hz mode - which affects *everything* on-screen, not just mpv. It also tries common multiples, eg. for a 24 Hz video it would also try setting your display to 48 Hz or 72 Hz modes, if available.

Note: This would also automatically toggle between eg. 60.00 Hz and 59.95 Hz, if your display can do both, so it can eliminate (in an entirely different way) some of what **fpsadjust.lua** was needed for.

This is also a static adjustment, since it again only updates at the beginning of playback, and also relies on accurate FPS information being available prior to playback - but it's important to understand the differences to **fpsadjust.lua**. Whereas **xrandr.lua** is more of a large-scale adjustment (eg. 60 Hz -> 48 Hz), **fpsadjust.lua** is only for fine adjustments (eg. 23.976 Hz -> 24.000 Hz) - and additionally, **xrandr.lua** only affects the display, whereas **fpsadjust.lua** only affects the video.

demuxer-mkv-fix-timestamps
--------------------------

This setting in mpv tries to fix another related problem - timestamp jitter. This only affects Matroska files (and by extension, WebM), because Matroska timestamps are rounded to 1ms precision - rather than being based on an arbitrary rational time basis like the one MP4 etc. have been using for ages. So for a 60 Hz video (which has a frame duration of 16.6ms), a Matroska file would store a series of frame durations like ``17 17 16 17 17 16`` which averages out to the true 16.6ms, but unfortunately introduces a lot of jitter and uncertainty in each individual timestamp.

The net result of this is that it makes display synchronization even more difficult, because even if you did have perfect clocks in your system, then you might still miss or duplicate a frame due to a frame being slightly ahead or slightly behind of your actual timestamps.

The ``--demuxer-mkv-fix-timestamps`` logic alleviates this by looking at the container FPS information if present, and if so overwriting the specified timestamps with the computed real timestamp as long as the two are within a set tolerance (ie. ±1ms real deviation). So in the above example, if the FPS header says “60 Hz”, then mpv would correct the series of frame durations to ``16.666 16.666 16.666 16.666 16.666 16.666``.

display-sync
------------

This is the “big new thing” available in mpv since [031555f](https://github.com/mpv-player/mpv/commit/031555fbe6cfdf6d0db3b0a5a316dd55efd75846), and it attacks the core problem not by polishing the rough edges, but instead by fundamentally changing the way playback works in mpv.

Instead of ignoring vsync timings and just “pushing” out frames whenever they should be displayed, the playback loop itself is now driven by the vsync - in other words, we constantly redraw (and wait for the buffers to be swapped) in an infinite loop, and then advance the internal playback position by ``(1 / display_FPS)`` every time.

A simpler way of putting it would be that: instead of timing being based on the audio clock, it's now based on the video clock (or “display” clock, hence the name). In essence, whereas before we were letting the audio play as fast as it wanted to (and adjusting the video to keep them in sync), we are now letting the video play as fast as it wants to - leaving the question of how to ensure audio/video stay synchronized.

To this end, there are multiple modes, expressed as possible parameters for ``--video-sync``, but the most interesting one is called ``display-resample``. If audio and video get out of sync, this mode will make the audio play slightly faster or slightly slower in order to keep them synchronized, and only resorts to dropping or duplicating video frames if stuff gets badly out of sync (eg. when the hardware is insufficient to keep up). The speed change defaults to 0.25%, which should be barely noticeable even to trained ears.

In addition to dynamically updating the audio speed, this mode will *also* minimize unnecessary frame drops by slightly changing the video playback speed (eg. for 23.976 Hz ⇔ 24.000 Hz mismatch - similar to **fpsadjust.lua**), and by correcting for jittering timestamps (as ``--demuxer-mkv-fix-timestamps`` did previously, but it's now part of the playback loop instead of the demuxer). So in other words, display-sync completely deprecates both **fpsadjust.lua** and ``--demuxer-mkv-fix-timestamps``, though it does not do any of what **xrandr.lua** tries to do.

Basically, ``--video-sync=display-resample`` makes video playback as perfect as possible, especially as the video framerate and display framerate get very close (eg. 60 Hz for both). In such a case, and assuming the file is not broken and the hardware is not too slow, it should guarantee *zero* dropped or duplicated frames. In essence, “perfect” playback.

It's important to note that, in order to avoid messing with playback completely when the file has broken or unusual timestamps, this mode automatically deactivates itself if the timestamps do not make sense (which should generally only affect badly broken files, eg. the ridiculously shitty twitch.tv streams, but also affects VFR content).

Finally, ``--video-sync=display-*`` currently comes with one important drawback: Due to OpenGL's rather severe limitations when it comes to timing, the only way to reliably figure out when vsyncs happen is to actually draw a frame on every vsync. The consequence of this is that, even for 24 Hz video, you need to draw frames at 60 Hz even if they are the same frame over and over again - thus increasing power usage by a factor of 2x-3x in such a case. Though this can be worked around by caching the frame result, that logic has not been implemented.
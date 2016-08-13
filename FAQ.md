### Does mpv have an official GUI?

No. But there is the OSC (on-screen-controller), which lets you control playback with the mouse. Requires mpv to be compiled with Lua support.

### Tearing

[Tearing](https://en.wikipedia.org/wiki/Screen_tearing) is a very annoying artifact that makes it look like the video has a horizontal line across the video. The video isn't properly joining on that line. The line can be fixed or moving. Sometimes it's not a line, but a bunch of blocks. It can be unnoticeable if there is no movement, but very apparent if the camera moves e.g. at low speed.

Tearing is generally not something a video player can do anything about. It depends on the hardware, drivers, the video output selected in mpv (VO), and possibly the desktop environment / compositor.

Changing the compositor settings can sometimes help with tearing.

* OSX

  Never seen it tearing.

* Windows

  Whether tearing happens with OpenGL may depend on the backend. Try various with ``--vo=opengl:backend=NAME``, where `NAME` is the name of the backend. `dxinterop` seems to perform best generally, but it will crash randomly with some older buggy Intel drivers.

  ``--vo=direct3d`` should never tear. (Maybe.)

* X11/Nvidia

 Nvidia should generally not tear. Sometimes, it tears in windowed mode, but not in fullscreen (solution unknown). There are additional problems on multimonitor systems.
    * Try enabling ``ForceFullCompositionPipeline``.
    * Try with and without a compositor.
    * Try disabling the composite extension in xorg.conf:

      ```
      Section "Extensions"
          Option "Composite" "Disable"
      EndSection
      ```


    * Set the performance mode to maximum performance. Energy saving often interferes with proper vo_opengl operation, and sometimes even appears to cause tearing.
    * Try ``--vo=vdpau``.

* X11/Intel

  Intel tears out of the box. Intel users on Linux are going to have a pretty bad time.
    * Try enabling SNA and the ``TearFree`` option.

      Unfortunately, this can cause stability issues - GL applications sometimes randomly crash. Somewhere, there's a claim that adding ``i915.semaphores=1`` to your kernel parameters fixes the crashes.
    * Try disabling SNA by using UXA (on older hardware).
    * Try ``--vo=xv:adaptor=N``, and try 0 or 1 for ``N``. This may fix tearing if the other methods fail, but keep in mind that using Xv with mpv is strongly discouraged.
    * Try ``--vo=vaapi``. Although this is Intel's native video output method, it seems to fix tearing only very rarely.

* X11/AMD

  AMD users on Linux are going to have a pretty bad time.

   * If you're getting tearing in multi-monitor setups, it seems there's nothing you can do about it. AMD drivers (apparently?) don't vsync across multiple monitors at all, let alone well.
   * You can possibly fix some tearing-related issues by using the ``Tear Free Desktop``, but this seems to degrade the display to 30 Hz operation and adds a lot of input latency.
   * For AMD cards it's generally a better idea to switch to the free radeon/mesa drivers and take the performance/feature hit, since the drivers provided by AMD are pretty unusable.

### I can't see the OSC/OSD/GUI!

The OSC requires Lua support. Install Lua (including development headers) and rebuild mpv.
If you didn't build mpv yourself, ask the packager to enable Lua.

Also note that the OSC is invisible by default, but it should appear once you move the mouse over the mpv window.

### Why do YouTube videos take forever to load?

Older ffmpeg versions didn't support DASH properly, update to ffmpeg to git/HEAD.

### (How) can I play YouTube playlists?

Pretty much like anything else, just pass the playlist URL to mpv. Note that you need a link to the actual playlist (`https://www.youtube.com/playlist?list=...`), NOT to a video in the playlist (`https://www.youtube.com/watch?v=...&list=...&index=...`). You can get that link by clicking on the title of the playlist on the right.

### If I click mpv, nothing happens.

mpv is a command line program and doesn't provide an actual GUI. You need to start it with a media file. On Windows, you can create a file association with the ``Open with…`` context menu. Also, if you start ``mpv.exe`` from ``explorer.exe``, it will enter [pseudo-gui mode](http://mpv.io/manual/master/#pseudo-gui-mode). For Linux, a ``mpv.desktop`` file is provided.

You can also start mpv with ``mpv --profile=pseudo-gui``. You play files by dropping them on the window.

### How can I change video quality on YouTube?

Check available format of video by **youtube-dl**:
```
youtube-dl --list-formats <link>
```
or 
```youtube-dl -F <link>```

For example:  
```
youtube-dl -F https://www.youtube.com/watch?v=SYM-RJwSGQ8
[info] Available formats for SYM-RJwSGQ8:
format code  extension  resolution note
...
251          webm       audio only DASH audio  149k , opus @160k, 4.29MiB
135          mp4        854x480    480p 1159k , avc1.4d401e, 25fps, video only, 16.02MiB
247          webm       1280x720   720p 1372k , vp9, 25fps, video only, 20.12MiB
136          mp4        1280x720   720p 2318k , avc1.4d401f, 25fps, video only, 30.37MiB
248          webm       1920x1080  1080p 2402k , vp9, 25fps, video only, 35.54MiB
137          mp4        1920x1080  1080p 3770k , avc1.640028, 25fps, video only, 55.70MiB
22           mp4        1280x720   hd720 , avc1.64001F,  mp4a.40.2@192k (best)
...
```
Choice format and type
```
mpv --ytdl-format <format code> https://www.youtube.com/watch?v=SYM-RJwSGQ8
```
For 1280x720:
```
mpv --ytdl-format 22 https://www.youtube.com/watch?v=SYM-RJwSGQ8
```
You can mix different video+audio:
```
mpv --ytdl-format [video format code] + [audio format code] link
```
For mp4 1080p video (3770k) and webm audio (149k, opus @160k):
```
mpv --ytdl-format 137+251 https://www.youtube.com/watch?v=SYM-RJwSGQ8
```

### Can I set volume over 100%?

On some systems, 100% is the maximum. You can put ``softvol=yes`` to force mpv's own volume filter. Then the ``softvol-max`` option controls the maximum. It's 130 by default.

Also consider using ``af=drc``, which helps especially with crappy speakers.

Note that in older versions of mpv, a volume of ``100`` always meant maximum, even if the maximum mapped to a linear gain factor over ``1.0``.

### How can I change volume using the mouse wheel?

By default, volume is changed by scrolling horizontally. If you want to use vertical scrolling for that (rather than seeking), put this in your `input.conf`:

```
MOUSE_BTN3 add volume 2
MOUSE_BTN4 add volume -2
```

### How can I find out the names and commands associated with each key?

Run mpv in [input test mode](http://mpv.io/manual/master/#options-input-test):

`mpv --input-test --force-window --idle`

### Is FFmpeg or Libav preferred for use with mpv?

Generally FFmpeg, simply because it has more features.

### How can I make mpv the default application to open movie files on OSX?

* Install mpv as an app with Homebrew:

    ```bash
    $ brew install mpv --with-bundle
    $ brew linkapps mpv
    ```

* Use [`duti`](https://github.com/moretension/duti) to associate files with application:

    ```bash
    $ brew install duti
    $ duti -s io.mpv api
    $ duti -s io.mpv mkv
    $ duti -s io.mpv mp4
    ```

[Source](https://github.com/kdeldycke/dotfiles/commit/380fed4e58070e10be9854636b8384960d3ee1d2).

### I want the old PulseAudio volume control back on Linux

With mpv 0.18.1, volume control was forced to softvol, and the ``--softvol`` option was removed. PulseAudio volume control (as in changing the per-client volume in the server) is not used anymore. If you want to use it, you have to switch you key-bindings manually to the audio output volume controls:

* open your input.conf
* add the following lines:

  ```
  9 add ao-volume -2
  0 add ao-volume 2
  ```
* or replace any occurrences of ``volume`` with ``ao-volume``
* don't forget that lines starting with ``#`` are commented (the default input.conf has all entries commented)
* note that mpv 0.18.1 had a bug that made PulseAudio "stuck" if the step was ``1`` and not ``2`` - this has been fixed in later versions

You can also grab all volume bindings from the [default input.conf)[https://raw.githubusercontent.com/mpv-player/mpv/master/etc/input.conf] to change all ``volume`` bindings.

Note this this also works on other audio outputs and platforms. Which kind of volume ``ao-volume`` controls depends entirely on the audio API. Some APIs make it the global system volume, some make it per-client or per-stream private volume.

For technically inclined people: there was also a branch adding change that would have allowed to change all key bindings with a single option, but it hasn't proven popular so far: https://github.com/mpv-player/mpv/commit/7621a028bf555c9ed0430501bc6eac2fa204114c
# User Scripts

Here is a list of scripts that users of mpv have published, adding functionality that is not part of the core mpv player.

**Warning:** all of these scripts are unofficial 3rd party scripts. Anyone can add their own script by editing this wiki.

## Lua

* **[autocrop](https://github.com/mpv-player/mpv/blob/master/TOOLS/lua/autocrop.lua)** - Automatically crop the video by using lavfi's cropdetect filter to detect black bars.

* **[autodeint](https://github.com/mpv-player/mpv/blob/master/TOOLS/lua/autodeint.lua)**- Automatically deinterlace the video by using lavfi's idet filter to detect interlaced content.

* **[autoload](https://github.com/mpv-player/mpv/blob/master/TOOLS/lua/autoload.lua)** - Automatically load playlist entries before and after the currently playing file, by scanning the directory.

* **[autosub](https://gist.github.com/selsta/ce3fb37e775dbd15c698)** - Automatically download subtitles using **subliminal**.

* **[betterchapters](https://gist.github.com/Hakkin/4f978a5c87c31f7fe3ae)** - Loads the next or previous playlist entry if there are no more chapters in the seek direction.

* **[convert_script](https://gist.github.com/Zehkul/25ea7ae77b30af959be0)** - Script to quickly convert and crop videos from within mpv, with a GUI.

* **[cycle-deinterlace-pullup](https://github.com/mpv-player/mpv/blob/master/TOOLS/lua/cycle-deinterlace-pullup.lua)** - Cycle between deinterlacing, pullup (IVTC), and both filters off.

* **[cycle_messages](https://gist.github.com/rrooij/59f57ff5f5a952e56bbb)** - Cycle between custom OSD messages.

* **[drc-control](https://github.com/mpv-player/mpv/blob/master/TOOLS/lua/drc-control.lua)**- Cycle through DRC (dynamic range compression) modes during runtime.

* **[dessubdb](https://github.com/demanuel/dessubdb/blob/master/mpv.lua)** - Download automatically subtitles from the thesubdb.com using [DESSubdb](https://github.com/demanuel/dessubdb)

* **[excerpt](https://github.com/lvml/mpv-plugin-excerpt)** - Allows you to quickly create excerpts from media files, you just have to set begin and end markers.

* **[find_subtitles](https://github.com/directorscut82/find_subtitles)** - (down)load subtitles with subliminal.

* **[fpsadjust](https://github.com/haasn/gentoo-conf/blob/nanodesu/home/nand/.mpv/scripts/fpsadjust.lua)** - Automatically adjust playback speed to synchronize the video to the display if possible (eg. by adjusting 23.976 Hz to 24 Hz for better compatibility with a 60 Hz display).

* **[last.fm scrobbler](https://github.com/l29ah/w3crapcli/blob/master/last.fm/mpv-lastfm.lua)** - Sends the information about playing tracks to [last.fm](http://last.fm/), see http://www.last.fm/help/faq?category=99 for more info.

* **[lua-mpris](https://github.com/dodo/lua-mpris)** - Adds mpris support to mpv.

* **[mpv_frame_info](https://github.com/Kagami/mpv_frame_info)** - Show frame info, similar to ffdshow's OSD.

* **[mpv_slicing](https://github.com/Kagami/mpv_slicing)** - Cut uncompressed fragments of the video.

* **[mpvmenu](https://github.com/nezumisama/mpvmenu)** - Adds a pop-up menu to mpv, which can be bound to a key or button

* **[notify](https://github.com/rohieb/mpv-notify)** - Adds desktop notifications to the mpv media player, which show metadata like artist, album name and track name when the track changes.

* **[ontop-playback](https://github.com/mpv-player/mpv/blob/master/TOOLS/lua/ontop-playback.lua)** - Disables the ontop property when pausing, and enables it again when unpausing the video, if it was disabled.

* **[pause-when-minimize](https://github.com/mpv-player/mpv/blob/master/TOOLS/lua/pause-when-minimize.lua)** - Pauses the player video when minimizing, and unpauses it when brought up again.

* **[skipchapters](https://github.com/haasn/gentoo-conf/blob/nanodesu/home/nand/.mpv/scripts/avail/skipchapters.lua)** - Automatically skip chapters matching a given list of regular expressions (eg. "OP" or "Opening").

* **[stats](https://github.com/Argon-/mpv-stats/)** - Display some statistics about the currently played file on-screen.

* **[streamcache](https://github.com/lvml/mpv-plugin-streamcache)** - Provides for more network-glitch-robust caching of live streams by adjusting replay speed.

* **[vo_battery](https://gist.github.com/selsta/9ac023688885053d42ca)** - (OS X) Choose the VO based on if the laptop is on battery or not.

* **[vo_battery](https://gist.github.com/ElegantMonkey/04924e899648e84f2e18)** - (Linux) Choose the VO based on if the laptop is on battery or not.

* **[xrandr](https://github.com/lvml/mpv-plugin-xrandr)** - Automatically sets the display refresh rate to the one best suitable for the video played

* **[zones](https://github.com/mpv-player/mpv/blob/master/TOOLS/lua/zones.lua)** - Handles commands depending on where the mouse pointer is at, mostly for mouse wheel handling.

If you want to write your own Lua scripts, have a look at the [documentation of mpv's Lua interface](https://github.com/mpv-player/mpv/blob/master/DOCS/man/lua.rst).


## Custom shaders

* **[sharpen complex 2](https://gist.github.com/zxx1/862dcfb171ddc3fa8832)**


## VapourSynth scripts

* **[mvtools](https://github.com/haasn/gentoo-conf/blob/nanodesu/home/nand/.mpv/filters/mvtools.vpy)** - Use [MVTools](https://github.com/dubhater/vapoursynth-mvtools)'s BlockFPS function to perform motion interpolation on the video in realtime.

* **[nnedi3](https://github.com/haasn/gentoo-conf/blob/nanodesu/home/nand/.mpv/filters/nnedi3.vpy)** - Use [NNEDI3](https://github.com/dubhater/vapoursynth-nnedi3) to double the resolution of the video. This always performs a single doubling. Note that the vapoursynth-nnedi3 filter is so slow that this practically can't be used in realtime, so it's not much use in practice.

* **[flash3kyuu](https://github.com/haasn/gentoo-conf/blob/nanodesu/home/nand/.mpv/filters/flash3kyuu.vpy)** - Use [flash3kyuu](https://github.com/SAPikachu/flash3kyuu_deband) to deband the video, with reasonable (mildly grainy) default settings. (Obsolete: mpv now ships with a similar debanding filter as shader)
# User Scripts

Here is a list of scripts that users of mpv have published, adding functionality that is not part of the core mpv player:

* **[autoload](https://github.com/mpv-player/mpv/blob/master/TOOLS/lua/autoload.lua)** - Automatically load playlist entries before and after the currently playing file, by scanning the directory.

* **[autosub](https://gist.github.com/selsta/ce3fb37e775dbd15c698)** - Automatically download subtitles using **subliminal**.

* **[convert_script](https://gist.github.com/Zehkul/25ea7ae77b30af959be0)** - Script to quickly convert and crop videos from within mpv, with a GUI.

* **[excerpt](https://github.com/lvml/mpv-plugin-excerpt)** - Allows you to quickly create excerpts from media files, you just have to set begin and end markers.

* **[fpsadjust](https://github.com/haasn/gentoo-conf/blob/master/home/nand/.mpv/scripts/fpsadjust.lua)** - Automatically adjust playback speed to synchronize the video to the display if possible (eg. by adjusting 23.976 Hz to 24 Hz for better compatibility with a 60 Hz display).

* **[last.fm scrobbler](https://github.com/l29ah/w3crapcli/blob/master/last.fm/mpv-lastfm.lua)** - Sends the information about playing tracks to [last.fm](http://last.fm/), see http://www.last.fm/help/faq?category=99 for more info.

* **[ontop-playback](https://gist.github.com/Shudouken/5f918ce6ded8b2034806)** - Disables the ontop property when pausing, and enables it again when unpausing the video, if it was disabled.

* **[skipchapters](https://github.com/haasn/gentoo-conf/blob/master/home/nand/.mpv/scripts/skipchapters.lua)** - Automatically skip chapters matching a given list of regular expressions (eg. "OP" or "Opening").

* **[streamcache](https://github.com/lvml/mpv-plugin-streamcache)** - Provides for more network-glitch-robust caching of live streams by adjusting replay speed.

* **[xrandr](https://github.com/lvml/mpv-plugin-xrandr)** - Automatically sets the display refresh rate to the one best suitable for the video played

* **[youtube-starttime](https://gist.github.com/Shudouken/0233126a99627be217a4)** - Seek to the given time if the URL contains a timestamp annotation (eg. ```#t=1m20s```).

If you want to write your own scripts, have a look at the [documentation of mpv's Lua interface](https://github.com/mpv-player/mpv/blob/master/DOCS/man/lua.rst).
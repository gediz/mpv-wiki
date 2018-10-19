# User Scripts

Here is a list of scripts that users of mpv have published, adding functionality that is not part of the core mpv player.
Most of these scripts are **unofficial 3rd party scripts**. Anyone can add their own script by editing this wiki. Scripts are usually placed in `~/.config/mpv/scripts/`.

## JavaScript

* **[Blackbox](https://github.com/VideoPlayerCode/mpv-tools/)**  
  Advanced, modular media browser, file manager and playlist manager for mpv.

* **[Colorbox](https://github.com/VideoPlayerCode/mpv-tools/)**  
  Apply color correction presets.

* **[Gallerizer](https://github.com/VideoPlayerCode/mpv-tools/)**  
  Image gallery autoloader for mpv.

* **[Leapfrog](https://github.com/VideoPlayerCode/mpv-tools/)**  
  Effortlessly jump through your playlist, with your own custom jump size and direction, including the ability to jump randomly. Excellent when queuing lots of images and using mpv as an image viewer.

* **[mpv-assrt](https://github.com/AssrtOSS/mpv-assrt)**  
  Download subtitles from [assrt.net](http://assrt.net), with interactive OSD menu.

* **[other.js](https://github.com/422658476/MPV-EASY-Player/blob/master/portable-data/scripts/other.js)**  
  Automatically save the adjusted volume (other parameters are also OK) to the specified configuration file under the specified path, use other scripts to get the volume value before starting mpv, and pass it to mpv to become the automatic volume function.

* **[screenshot-to-clipboard](https://github.com/zc62/mpv-scripts/blob/master/screenshot-to-clipboard.js)**  
  Generates a temp screenshot file on desktop then copy to clipboard. (Windows only)

* **[seek-show-position](https://github.com/stax76/mpvnet/blob/master/Scripts/seek-show-position.js)**  
  Shows the position and duration when seeking (formatted as: 00:00 / 120:00)

* **[VideoPlayerCode's Modules.js (for developers)](https://github.com/VideoPlayerCode/mpv-tools/tree/master/scripts/modules.js)**  
  Tons of pre-written, open source JavaScript modules which helps you rapidly create your own JS user scripts (including a very helpful [script config](https://github.com/VideoPlayerCode/mpv-tools/blob/master/scripts/modules.js/Options.js) system based on mpv's Lua `mp.options` API). All modules are free to use (and extend) in your own scripts!



## Lua Scripts

* **[acompressor](https://github.com/mpv-player/mpv/blob/master/TOOLS/lua/acompressor.lua)**  
  Dynamic range compressor using acompressor ffmpeg filter with controls to dynamically adjust parameters.

* **[audio-balance](https://github.com/wiiaboo/mpv-scripts/blob/master/audio-balance.lua)**  
  Port of mpv's balance property to FFmpeg lavfi pan filter.

* **[audio-file-keys](https://github.com/fbriere/mpv-scripts/blob/master/scripts/audio-file-keys.lua)**  
  Automatically apply key bindings when playing audio files.

* **[autocrop](https://github.com/mpv-player/mpv/blob/master/TOOLS/lua/autocrop.lua)**  
  Automatically crop the video by using lavfi's cropdetect filter to detect black bars.

* **[autoloop](https://github.com/zc62/mpv-scripts/blob/master/autoloop.lua)**  
  Automatically loops files that are under a given duration (default 5 seconds).

* **[autosave](https://gist.github.com/Hakkin/5489e511bd6c8068a0fc09304c9c5a82)**  
  Periodically saves "watch later" data during playback, rather than only saving on quit.

* **[autospeed](https://github.com/kevinlekiller/mpv_scripts/blob/master/autospeed/)**  
  To adjust monitor refresh rate and video speed for almost 1:1 playback. (*nix)

* **[autospeedwin](https://github.com/kevinlekiller/mpv_scripts/tree/master/autospeedwin)**  
  To adjust monitor refresh rate and video speed for almost 1:1 playback. (Windows)

* **[autodeint](https://github.com/mpv-player/mpv/blob/master/TOOLS/lua/autodeint.lua)**  
  Automatically deinterlace the video by using lavfi's idet filter to detect interlaced content.

* **[auto-keep-gui-open](https://github.com/VideoPlayerCode/mpv-tools/)**  
  Intelligently switches mpv's "keep-open" behavior based on whether you are running in video-mode or audio-only mode.

* **[autoload](https://github.com/mpv-player/mpv/blob/master/TOOLS/lua/autoload.lua)**  
  Automatically load playlist entries before and after the currently playing file, by scanning the directory.

* **[auto-profiles](https://github.com/wiiaboo/mpv-scripts/blob/master/auto-profiles.lua)**  
  Automatically apply profiles based on predicates written as Lua expressions.

* **[autosub](https://gist.github.com/selsta/ce3fb37e775dbd15c698)**  
  Automatically download subtitles using **subliminal**.

* **[betterchapters](https://gist.github.com/Hakkin/4f978a5c87c31f7fe3ae) ([update](https://github.com/mpv-player/mpv/issues/4738#issuecomment-321298846))**  
  Loads the next or previous playlist entry if there are no more chapters in the seek direction.

* **[blackout](https://github.com/dya-tel/mpv-scripts)**  
  A fast crossplatfrom boss-key, but without window minimization (and possible problems with some VO drivers).

* **[blur-edges](https://github.com/occivink/mpv-scripts#blur-edgeslua)**  
  Replace black bars with a blurry copy of the video

* **[bookmark](https://github.com/sorayuki-winter/mpv-plugin-bookmark)**  
  Record and resume last play in current playing folder

* **[boss-key](https://github.com/detuur/mpv-scripts)**  
  **UPDATED VERSION**. Minimise and pause video at the same time. Windows/Linux. Eliminated the time lag in previous versions.

* **[Tcl/Tk context menu](https://gist.github.com/avih/bee746200b5712220b8bd2f230e535de)**  
  Configurable context-menu based on Tcl/Tk, for *nix/Windows and probably macOS too.

* **[clock](https://gitlab.com/mozbugbox/mpv-script-mozbugbox)**  
  Constantly show current time on the lower left corner of the video screen.

* **[convert_script](https://gist.github.com/Zehkul/25ea7ae77b30af959be0)**  
  Script to quickly convert and crop videos from within mpv, with a GUI.

* **[copy-permalink](https://gist.github.com/olejorgenb/a5194d9bc183dbe0bfb02aac18fe37f9)**  
  Copy `mpv --time=<current-position> <path-playing>` to clipboard. Useful for sharing when playing URLs.

* **[crop](https://github.com/occivink/mpv-scripts#croplua)**  
  Crop the video by defining the target rectangle with the cursor

* **[curvesman](https://gitlab.com/mozbugbox/mpv-script-mozbugbox)**  
  Manipulate color curves filter of FFmpeg with hotkeys. Brighten up color, change color temperature/tone, hopefully more. Adjust yellow light tone to white light tone.

* **[cycle-audio-device](https://gist.github.com/bitingsock/ad58ee5da560ecb922fa4a867ac0ecfd)**  
  Cycle through available audio devices with key binds.

* **[cycle-deinterlace-pullup](https://github.com/mpv-player/mpv/blob/master/TOOLS/lua/cycle-deinterlace-pullup.lua)**  
  Cycle between deinterlacing, pullup (IVTC), and both filters off.

* **[cycle-denoise](https://gist.github.com/myfreeer/d744c445aa71c0eeb165ca39cf6c0511)**  
  Cycle between lavfi's denoise filters (press n)

* **[cycle_messages](https://gist.github.com/rrooij/59f57ff5f5a952e56bbb)**  
  Cycle between custom OSD messages.

* **[cycle-video-rotate](https://github.com/VideoPlayerCode/mpv-tools/)**  
  Allows you to perform video rotation which perfectly cycles through all 360 degrees without any glitches.

* **[dessubdb](https://github.com/demanuel/dessubdb/blob/master/mpv.lua)**  
  Download automatically subtitles from the thesubdb.com using [DESSubdb](https://github.com/demanuel/dessubdb).

* **[delete-file](https://github.com/zenyd/mpv-scripts)**  
  Provides the ability to delete files being played through mpv

* **[locate-file](https://github.com/nimatrueway/mpv-locatefile-lua-script)**  
  Locate current media file on your OS file browser 

* **[delogo](https://github.com/b4zz4/mpv-delogo)**  
  It removes the logo of the channels in a video (press n)

* **[deframe](https://github.com/b4zz4/mpv-deframe)**  
  It removes the frame of youtube videos (press g)

* **[drag-to-pan](https://github.com/occivink/mpv-image-viewer)**  
  Pan the current video or image with the cursor.

* **[easycrop](https://github.com/aidanholm/mpv-easycrop)**  
  Manually crop a video during playback.

* **[encode](https://github.com/occivink/mpv-scripts#encodelua)**  
  Re-encode or remux part of the current video. Can also preserve some filters, such as "crop".

* **[equalizer](https://gist.github.com/avih/41acff712abd32e1f436235388c8b523)**  
  5-bands equalizer with colorful display.

* **[excerpt](https://github.com/lvml/mpv-plugin-excerpt)**  
  Allows you to quickly create excerpts from media files, you just have to set begin and end markers.

* **[fastforward](https://github.com/jgreco/mpv-scripts/blob/master/fastfoward.lua)**  
  Instead of skipping forward in media files, speed up the playback for a few seconds.  Playback speed decays back to 1x after a few seconds.  Tap rapidly or hold down to go faster.

* **[Filenavigator](https://github.com/donmaiq/mpv-filenavigator)**  
  Navigate directories and open files from your system.

* **[filter-test](https://gitlab.com/mozbugbox/mpv-script-mozbugbox)**  
  Test mpv/FFmpeg video filter(vf) strings with editable popup dialog. 

* **[find_subtitles](https://github.com/directorscut82/find_subtitles)**  
  (Down)load subtitles with subliminal.

* **[firequalizer15](https://github.com/mfcc64/mpv-scripts/blob/master/firequalizer15.lua)**  
  Linear phase 15-bands equalizer.

* **[fix_sub_timing](https://github.com/wiiaboo/mpv-scripts/blob/master/fix-sub-timing.lua)**  
  Compute the correct speed/delay of subtitles by manually synching two points in time.

* **[fpsadjust](https://github.com/haasn/gentoo-conf/blob/xor/home/nand/.mpv/scripts/avail/fpsadjust.lua)**  
  Automatically adjust playback speed to synchronize the video to the display if possible (eg. by adjusting 23.976 Hz to 24 Hz for better compatibility with a 60 Hz display).
**Obsolete:** mpv now has a native display-sync option.

* **[fuzzydir](https://github.com/dya-tel/mpv-scripts)**  
  Allows using wildcards for `sub-file-paths` and `audio-file-paths`.

* **[gallery-view](https://github.com/occivink/mpv-gallery-view)**  
  View playlist in a grid view of thumbnails.

* **[gpufreq](https://gist.github.com/CounterPillow/0b764ed14c609024c9188383f7dce033)**  
  Show current and maximum GPU frequencies for GPUs using the DRM stack on Linux.

* **[KDialog-open-files](https://gist.github.com/ntasos/d1d846abd7d25e4e83a78d22ee067a22)**  
Use KDE's KDialog to add files to playlist, subtitles to playing video or open URLs.

* **[image-viewer](https://github.com/occivink/mpv-image-viewer)**  
   Configurations, scripts and tips for using mpv as an image viewer.

* **[interSubs](https://github.com/oltodosel/interSubs)**  
  Interactive subtitles. Instantly translate selected word/sentence. Works on Linux, macOS.

* **[last.fm scrobbler](https://github.com/l29ah/w3crapcli/blob/master/last.fm/mpv-lastfm.lua)**  
  Sends the information about playing tracks to [last.fm](http://last.fm/), see http://www.last.fm/help/faq?category=99 for more info.

* **[live-filters](https://github.com/hdbhdb/mpv-live-filters)**  
  Add, remove or toggle ffmpeg video filters during mpv playback.

* **[local-language](https://github.com/422658476/MPV-EASY-Player/blob/master/portable-data/scripts/local-language.lua)**  
  Let the text displayed by mpv osd become the language you are most familiar with, that is, language localization, such as 【volume: 100%】 becomes 【音量:100%】.

* **[lua-mpris](https://github.com/dodo/lua-mpris)**  
  Adds mpris support to mpv.

* **[mark-chapter](https://github.com/thebombzen/scripts/blob/master/src/lua/markchapter.lua)**  
  Temporarily mark the current playback position as a chapter so you can seek to it later. Don't forget to edit input.conf to give it a keybinding.

* **[createchapter](https://github.com/shinchiro/mpv-createchapter)**  
  Similar as `mark-chapter` but with ability to export valid xml file.

* **[minesweeper](https://github.com/wiiaboo/mpv-scripts/blob/master/mines.lua)**  
  Minesweeper game.

* **[mpegts-truncate](https://github.com/hoehermann/mpv-mpegts-truncate)**  
  Removes beginning of MPEG TS file up to current position without re-writing the whole file.

* **[mpv-bookmarker](https://github.com/nimatrueway/mpv-bookmark-lua-script)**  
  Bookmark your favorite time on media files

* **[mpv-Change-OSD-Media-Title](https://github.com/nmoorthy1/mpv-Change-OSD-Media-Title)**  
  Displays filename, percentage watched, current chapter, and number of frames dropped in the OSD media title and updates it whenever one of the values has changed.

* **[mpv_crop_script](https://github.com/TheAMM/mpv_crop_script)**  
  Take cropped screenshots directly within mpv, without the need for external dependencies.

* **[mpv_discordRPC](https://github.com/noaione/mpv-discordRPC)**  
  Discord RPC integration for mpv using lua-discordRPC as base.

* **[mpv_discordRPC](https://github.com/cniw/mpv-discordRPC) *(alternative version)***  
  Discord Rich Presence integration for mpv Media Player. Added some features and support: Linux, MacOS and Windows.

* **[mpv_frame_info](https://github.com/Kagami/mpv_frame_info)**  
  Show frame info, similar to ffdshow's OSD.

* **[mpv-history](https://gist.github.com/garoto/e0eb539b210ee077c980e01fb2daef4a)**  
  Simple played media logger. Will generate a `mpvhistory.log` in the default mpv config folder (%APPDATA%/mpv/ or $HOME/.config/mpv/) in the format `[$DATE $TIME] $PATH ($?MEDIA-TITLE)`. Only tested on Windows.

* **[mpv_slicing](https://github.com/Kagami/mpv_slicing)**  
  Cut uncompressed fragments of the video.

* **[mpv_thumbnail_script](https://github.com/TheAMM/mpv_thumbnail_script)**  
  Show preview thumbnails when hovering over the seekbar, without the need for external dependencies.

* **[mpv-txt](https://github.com/jgreco/mpv-txt)**  
  Play text files using text-to-speech (TTS). (Works on Linux, MacOS; see Dependencies).

* **[mpvcontextmenu](https://gitlab.com/carmanaught/mpvcontextmenu)**  
  Comprehensive context-menu forked from [Tcl/Tk context menu](https://gist.github.com/avih/bee746200b5712220b8bd2f230e535de). Uses other scripts (see Requirements).

* **[mpvmenu](https://github.com/nezumisama/mpvmenu)**  
  Adds a pop-up menu to mpv, which can be bound to a key or button

* **[multi-command-if](https://github.com/VideoPlayerCode/mpv-tools/)**  
  Very powerful conditional logic and multiple action engine for your keybindings, without having to write a single line of code!

* **[myshows](https://github.com/gim-/mpv-plugin-myshows)**  
  Marks currently watched episode on MyShows website.

* **[nextfile](https://github.com/donmaiq/mpv-nextfile)**  
  Force opens next or previous file in the currently playing files folder.

* **[notify](https://github.com/rohieb/mpv-notify)**  
  Adds desktop notifications to the mpv media player, which show metadata like artist, album name and track name when the track changes.

* **[ontop-playback](https://github.com/mpv-player/mpv/blob/master/TOOLS/lua/ontop-playback.lua)**  
  Disables the ontop property when pausing, and enables it again when unpausing the video, if it was disabled. Change it only when the player is not in fullscreen to prevent screen flickering.

* **[open-file-dialog](https://github.com/rossy/mpv-open-file-dialog)**  
  (Windows) Launches a regular Windows file open dialog for loading videos.

* **[osc-style](https://github.com/422658476/MPV-EASY-Player/tree/master/mpv-easy-data/osc-style)**  
  Change the mpv osc to a more beautiful and practical look, which is the osc theme feature, a variety of styles to choose from,this is a [tutorial and a preview](https://github.com/422658476/MPV-EASY-Player#%E7%9C%8B%E5%88%B0%E4%B8%8A%E9%9D%A2%E5%9B%BE%E4%B8%8A%E8%BF%99%E4%BA%9Bosc%E6%A0%B7%E5%BC%8F%E4%BA%86%E5%90%97%E5%AE%83%E4%BB%AC%E4%B8%8D%E4%BB%85%E5%8F%AF%E4%BB%A5%E5%AD%98%E5%9C%A8%E4%BA%8Empv-easy-player%E4%B8%AD%E4%BD%A0%E4%BD%BF%E7%94%A8%E7%9A%84mpv%E7%9A%84osc%E4%B9%9F%E5%8F%AF%E4%BB%A5%E5%8F%98%E6%88%90%E8%BF%99%E6%A0%B7).

* **[osd-bar](https://github.com/422658476/MPV-EASY-Player/blob/master/portable-data/scripts/osd-bar.lua)**  
  Always show osd progress bar, with the more beautiful color matching in the [configuration file](https://github.com/422658476/MPV-EASY-Player/blob/master/mpv-easy-data/rjno1.conf), you can make the osd progress bar display the current progress at the bottom of the window beautifully,this is a [preview](https://raw.githubusercontent.com/422658476/MPV-EASY-Player/master/img/mpv-easy-player-osd-bar-lua.jpg).

* **[osd-clock](https://github.com/blue-sky-r/mpv/blob/master/scripts/osd-clock.lua)**  
  Periodically shows OSD clock (many configurable options).

* **[pause-indicator](https://gist.github.com/torque/9dbc69543118347d2e5f43239a7e609a)**  
  Displays a momentary icon that flashes in the middle of the screen, similar to YouTube.

* **[pause-when-minimize](https://github.com/mpv-player/mpv/blob/master/TOOLS/lua/pause-when-minimize.lua)**  
  Pauses the player video when minimizing, and unpauses it when brought up again.

* **[peerflix-hook](https://gist.github.com/ElegantMonkey/bba287693830055a6bad90081c1ad4e2)**  
  Allows streaming of magnet links using peerflix, similar to youtube-dl.

* **[pitchcontrol](https://github.com/FichteFoll/mpv-scripts/blob/master/pitchcontrol.lua)**  
  Adjusts audio pitch in half-tone steps.

* **[Playlistmanager](https://github.com/donmaiq/Mpv-Playlistmanager)**  
  Helps with creating playlists, saving them and modifying your current playlist.

* **[playlistnoplayback](https://github.com/422658476/MPV-EASY-Player/blob/master/portable-data/scripts/playlistnoplayback.lua)**  
  If you enable the save play history and progress function, this lua script can solve the problem of automatically jumping to the previous playback progress when playing the next file when playing the playlist, that is, let the playlist always play the next file from the beginning every time. the limitations of this script, please see the comments section in the content.

* **[progressbar](https://github.com/torque/mpv-progressbar)**  
  A minimalistic OSC replacement. It provides a small, unintrusive progress bar that persists at the bottom of the video window.

* **[quick-scale](https://github.com/VideoPlayerCode/mpv-tools/)**  
  Quickly scale the video player to a target size, with full control over target scale and max scale. Helps you effortlessly resize a video to fit on your desktop, or any other video dimensions you need!

* **[redshift_toggle](http://repo.or.cz/q3cpma-dotfiles.git/blob_plain/HEAD:/.config/mpv/scripts/redshift_toggle.lua)**  
  Toggle redshift when loading a video file and when reaching the end of said file.

* **[reload](https://github.com/4e6/mpv-reload)**  
  When an online video is stuck during buffering or got slow CDN source, restarting often helps. This script provides automatic reloading of videos that didn't have buffering progress for some time, keeping the current time position. It also adds `Ctrl+r` keybinding to reload video manually.

* **[repl](https://github.com/rossy/mpv-repl)**  
  A REPL for input commands that is displayed on the video window.

* **[rubberband_helper](https://github.com/jgreco/mpv-scripts/blob/master/rubberband_helper.lua)**  
  [rubberband](https://github.com/lachs0r/rubberband) is great for keeping voices intelligible when the video playback is speed up, but it consumes a fair amount of CPU.  This script allows you to degrade the audio filter back to scaletempo when playback speeds are high enough to make rubberband pointless.  **Note:** mpv must be built with rubberband support; see `mpv --af=rubberband=help`

* **[save-sub-delay](https://github.com/zc62/mpv-scripts/blob/master/save-sub-delay.lua)**  
  This script saves the sub-delay quantity for each file. When next time the file is opened, sub-delay is automatically restored.

* **[seek-to](https://github.com/occivink/mpv-scripts#seek-tolua)**  
  Seek to an absolute timestamp specified via keyboard input.

* **[show-filename](https://github.com/yuukidach/mpv-scripts)**  
  Show the name of the current playing file.

* **[show-stream-title](https://github.com/blue-sky-r/mpv/blob/master/scripts/show-stream-title.lua)**  
  Show OSD stream/channel title when switching the IPTV channels from m3u playlist.

* **[simple-loader](https://github.com/fhlfibh/simple-loader)**  
  (Linux) Browse dirs and files on OSD, and launch them with mpv.

* **[simple-mpv-webui](https://github.com/open-dynaMIX/simple-mpv-webui)**  
  Web-based remote control.

* **[skipchapters](https://github.com/haasn/gentoo-conf/blob/xor/home/nand/.mpv/scripts/avail/skipchapters.lua)**  
  Automatically skip chapters matching a given list of regular expressions (eg. "OP" or "Opening").

* **[skiptofade](https://gist.github.com/bossen/3cfe86a6cdd61452dbb96865128fb327)**  
  Seeks forward until a black screen appears. Built to skip openings. Uses the lavfi blackdetect filter. 

* **[sopcast](https://github.com/Akemi/mpv-sopcast-hook)**  
  Adds support for sop:// urls.

* **[speed-transition](https://github.com/zenyd/mpv-scripts)**  
  Increases playback speed if a subtitle will not be displayed soon. Resumes normal speed just before the subtitle shows up.

* **[speed-transition-Audio](https://github.com/zenyd/mpv-scripts/blob/master/speed-transition.lua)**  
  Experiment similar to [speed-transition](https://github.com/zenyd/mpv-scripts). changes playback speed based on volume thresholds.

* **[subit](https://github.com/wiiaboo/mpv-scripts/blob/master/subit.lua)**  
  Yet another script for downloading subtitles using subliminal. Supports better customization of options, such as easy language selection, authentication for providers that need it, and support for URLs.

* **[subselect Tk](https://github.com/zenyd/mpv-scripts)**  
  Download subtitles with a GUI - select the one you want and automatically load them up in mpv. Supports searching for arbitrary names and different subtitle languages. Works on Windows and Linux, possibly macOS.

* **[sub-cut](https://github.com/kelciour/mpv-scripts/blob/master/sub-cut.lua)**  
  Extract a part of the video as audio or video with subtitles.

* **[sub-bilingual](https://github.com/kelciour/mpv-scripts/blob/master/sub-bilingual.lua)**  
  Generate bilingual subtitles.

* **[sub-bookmarks](https://github.com/kelciour/mpv-scripts/blob/master/sub-bookmarks.lua)**  
  Save current position and subtitles in .txt file.

* **[sub-export](https://github.com/kelciour/mpv-scripts/blob/master/sub-export.lua)**  
  Extract selected subtitles from .mkv file.

* **[sub-playback](https://github.com/kelciour/mpv-scripts/blob/master/sub-playback.lua)**  
  Add interactive move, i.e. automatically pause at the end of the fragment with option to continue playback or replay it again with or without subtitles.

* **[sub-replay](https://github.com/kelciour/mpv-scripts/blob/master/sub-replay.lua)**  
  Replay previous sentence.

* **[sub-search](https://github.com/kelciour/mpv-scripts/blob/master/sub-search.lua)**  
  Search for phrase in subtitles and skip to it.

* **[sub-sentences](https://github.com/kelciour/mpv-scripts/blob/master/sub-sentences.lua)**  
  Generate subtitles with sentences.

* **[sub-voracious](https://github.com/kelciour/mpv-scripts/blob/master/sub-voracious.lua)**  
  Reading and listening practice.

* **[subs2srs](https://github.com/kelciour/mpv-scripts/blob/master/subs2srs.lua)**  
  Automatically add new card in Anki with audio, picture and text.

* **[stats](https://github.com/Argon-/mpv-stats/)**  
  Display some statistics about the currently played file on-screen.

* **[streamcache](https://gitlab.com/lvml/mpv-plugin-streamcache)**  
  Provides for more network-glitch-robust caching of live streams by adjusting replay speed.

* **[time](https://github.com/mustaqimM/mpv-scripts/blob/master/time.lua)**  
  Shows the current time or the time at which playback will end.

* **[timer](https://github.com/AdamD2/mpv-timer)**  
  Allows the user to set a starting time and an ending time and see the time elapsed between those points with millisecond precision.

* **[tree-profiles](https://github.com/fbriere/mpv-scripts/blob/master/scripts/tree-profiles.lua)**  
Automatically apply profiles to certain directories or files.

* **[total_playtime](https://github.com/oltodosel/mpv-scripts/blob/master/total_playtime.lua)**  
Shows total playtime of current playlist.

* **[trueautosub](https://github.com/fullmetalsheep/mpv-iina-scripts)**  
Improved fork of autosub, Automatically downloads subtitles if not present using **subliminal**. (osx/linux only)

* **[tv-output](https://github.com/blue-sky-r/mpv/blob/master/scripts/tv.lua)**  
  (Linux) TV output handling - activate on mpv playback and deactivate on mpv shutdown.

* **[unseen-playlistmaker](https://github.com/donmaiq/unseen-playlistmaker)**  
  Keeps track of watched files locally, and creates playlists of unwatched files.

* **[visualizer](https://github.com/mfcc64/mpv-scripts/blob/master/visualizer.lua)**  
  Various audio visualization.

* **[vo_battery](https://gist.github.com/ElegantMonkey/04924e899648e84f2e18)**  
  (Linux) Choose the VO based on if the laptop is on battery or not.

* **[webm](https://github.com/ElegantMonkey/mpv-webm)**  
  Simple WebM maker for mpv, with no external dependencies.

* **[xrandr](https://github.com/lvml/mpv-plugin-xrandr)**  
  Automatically sets the display refresh rate to the one best suitable for the video played

* **[youtube-quality](https://github.com/jgreco/mpv-youtube-quality)**  
  A menu for changing youtube video quality (ytdl-format) on the fly, as though you were using the web player.

* **[zones](https://github.com/wiiaboo/mpv-scripts/blob/master/zones.lua)**  
  Handles commands depending on where the mouse pointer is at, mostly for mouse wheel handling.

* **[~~addfile~~](https://github.com/devnikor/mpv-conf/blob/master/scripts/addfile.lua)**  
  ~~(OS X) Add subtitle or audio track to playing video file~~

If you want to write your own Lua scripts, have a look at the [documentation of mpv's Lua interface](https://mpv.io/manual/master/#lua-scripting).


## User Shaders

* **[LumaSharpenHook](https://gist.github.com/voltmtr/8b4404b4e23129b226b9e64863d3e28b)**  
  A sharpen filter similar to using Unsharp Mask in Photoshop ported from SweetFX shader pack.

* **[SSimDownscaler, SSimSuperRes, Krig, Adaptive Sharpen, etc.](https://gist.github.com/igv)**  
  * SSimDownscaler: Perceptually based downscaler. More information is [here](https://graphics.ethz.ch/~cengizo/imageDownscaling.htm).
  * SSimSuperRes: The aim of this shader is to make corrections to the image upscaled by mpv built-in scaler (removes ringing artifacts, restores original sharpness, etc).
  * Krig: Chroma scaler that uses luma information for high quality upscaling.

* **[Noise](https://github.com/haasn/gentoo-conf/blob/xor/home/nand/.mpv/shaders/noise.glsl)**  
  Adds a tunable amount of grayscale noise to the output.

* **[Antiringing](https://github.com/haasn/gentoo-conf/blob/xor/home/nand/.mpv/shaders/antiring.hook)**  
  This is an antiringing filter that works by clamping to the local neighbourhood. Sort of inspired by the mpv built-in antiringing algorithm, but it's extended in such a way that it also works well for polar (EWA) filters, which the mpv built-in algorithm does not support at all.

* **[nnedi3, superxbr and ravu](https://github.com/bjin/mpv-prescalers/tree/master)**  
  User shaders for prescaling. These shaders should cover most functionality that `prescale-luma=` used to provide.

* **[FSRCNN](https://github.com/igv/FSRCNN-TensorFlow/releases)**  
  Prescaler based on layered convolutional networks.

* **[un360](https://gist.github.com/tesu/196db5421559de3e9555d4f9da9d847d)**  
  Converts equirectangular 360 degree video to be watchable, at a fixed perspective.
  
## VapourSynth Scripts

* **[mvtools](https://github.com/haasn/gentoo-conf/blob/xor/home/nand/.mpv/filters/mvtools.vpy)**  
  Use [MVTools](https://github.com/dubhater/vapoursynth-mvtools)'s BlockFPS function to perform motion interpolation on the video in realtime.

* **[nnedi3](https://github.com/haasn/gentoo-conf/blob/xor/home/nand/.mpv/filters/nnedi3.vpy)**  
  Use [NNEDI3](https://github.com/dubhater/vapoursynth-nnedi3) to double the resolution of the video. This always performs a single doubling. Note that the vapoursynth-nnedi3 filter is so slow that this practically can't be used in realtime, so it's not much use in practice. 

* **[flash3kyuu](https://github.com/haasn/gentoo-conf/blob/xor/home/nand/.mpv/filters/flash3kyuu.vpy)**  
  Use [flash3kyuu](https://github.com/SAPikachu/flash3kyuu_deband) to deband the video, with reasonable (mildly grainy) default settings. 
**Obsolete:** mpv now ships with a similar debanding filter as shader.


## C Plugins

* **[mpv-mpris](https://github.com/hoyon/mpv-mpris)**  
  Adds support for MPRIS2 protocol


## Other

* **[play-with](https://github.com/grmat/play-with)**  
  A WebExtension that can open a video stream on a web page with an external player.

* **[playphrase](https://github.com/kelciour/playphrase)**  
  Search and play phrases from movies and audiobooks.

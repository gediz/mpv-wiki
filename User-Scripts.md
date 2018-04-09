# User Scripts

Here is a list of scripts that users of mpv have published, adding functionality that is not part of the core mpv player.
Most of these scripts are **unofficial 3rd party scripts**. Anyone can add their own script by editing this wiki. Scripts are usually placed in `~/.config/mpv/scripts/`.

## JavaScript

* **[Blackbox](https://github.com/SteveJobzniak/mpv-tools)**  
  Advanced, modular media browser, file manager and playlist manager for mpv.

* **[Leapfrog](https://github.com/SteveJobzniak/mpv-tools)**  
  Effortlessly jump through your playlist, with your own custom jump size and direction, including the ability to jump randomly. Excellent when queuing lots of images and using mpv as an image viewer.

* **[mpv-assrt](https://github.com/AssrtOSS/mpv-assrt)**  
  Download subtitles from [assrt.net](http://assrt.net), with interactive OSD menu.

* **[screenshot-to-clipboard](https://github.com/zc62/mpv-scripts/blob/master/screenshot-to-clipboard.js)**  
  Generates a temp screenshot file on desktop then copy to clipboard. (Windows only)

* **[seek-show-position](https://github.com/stax76/mpvnet/blob/master/Scripts/seek-show-position.js)**  
  Shows the position and duration when seeking (formatted as: 00:00 / 120:00)

* **[SteveJobzniak's Modules.js (for developers)](https://github.com/SteveJobzniak/mpv-tools/tree/master/scripts/modules.js)**  
  Tons of pre-written, open source JavaScript modules which helps you rapidly create your own JS user scripts (including a very helpful [script config](https://github.com/SteveJobzniak/mpv-tools/blob/master/scripts/modules.js/Options.js) system based on mpv's Lua `mp.options` API). All modules are free to use (and extend) in your own scripts!



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

* **[auto-keep-gui-open](https://github.com/SteveJobzniak/mpv-tools)**  
  Intelligently switches mpv's "keep-open" behavior based on whether you are running in video-mode or audio-only mode.

* **[autoload](https://github.com/mpv-player/mpv/blob/master/TOOLS/lua/autoload.lua)**  
  Automatically load playlist entries before and after the currently playing file, by scanning the directory.

* **[auto-profiles](https://github.com/wm4/mpv-scripts/blob/master/auto-profiles.lua)**  
  Automatically apply profiles based on predicates written as Lua expressions.

* **[autosub](https://gist.github.com/selsta/ce3fb37e775dbd15c698)**  
  Automatically download subtitles using **subliminal**.

* **[betterchapters](https://gist.github.com/Hakkin/4f978a5c87c31f7fe3ae)**  
  Loads the next or previous playlist entry if there are no more chapters in the seek direction.

* **[blur-edges](https://github.com/occivink/mpv-scripts#blur-edgeslua)**  
  Replace black bars with a blurry copy of the video

* **[bookmark](https://github.com/sorayuki-winter/mpv-plugin-bookmark)**  
  Record and resume last play in current playing folder

* **[boss-key](https://gist.github.com/detuur/7ea3609b8826d0e6f6bbc730d54a963c)**  
  Minimise and pause video at the same time, Windows only so far.

* **[Tcl/Tk context menu](https://gist.github.com/avih/bee746200b5712220b8bd2f230e535de)**  
  Configurable context-menu based on Tcl/Tk, for *nix/Windows and probably macOS too.

* **[convert_script](https://gist.github.com/Zehkul/25ea7ae77b30af959be0)**  
  Script to quickly convert and crop videos from within mpv, with a GUI.

* **[crop](https://github.com/occivink/mpv-scripts#croplua)**  
  Crop the video by defining the target rectangle with the cursor

* **[cycle-audio-device](https://gist.github.com/bitingsock/ad58ee5da560ecb922fa4a867ac0ecfd)**  
  Cycle through available audio devices with key binds.

* **[cycle-deinterlace-pullup](https://github.com/mpv-player/mpv/blob/master/TOOLS/lua/cycle-deinterlace-pullup.lua)**  
  Cycle between deinterlacing, pullup (IVTC), and both filters off.

* **[cycle-denoise](https://gist.github.com/myfreeer/d744c445aa71c0eeb165ca39cf6c0511)**  
  Cycle between lavfi's denoise filters (press n)

* **[cycle_messages](https://gist.github.com/rrooij/59f57ff5f5a952e56bbb)**  
  Cycle between custom OSD messages.

* **[cycle-video-rotate](https://github.com/SteveJobzniak/mpv-tools)**  
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

* **[drag-to-pan](https://github.com/occivink/mpv-scripts#drag-to-panlua)**  
  Pan the current video or image with the cursor.

* **[easycrop](https://github.com/aidanholm/mpv-easycrop)**  
  Manually crop a video during playback.

* **[encode](https://github.com/occivink/mpv-scripts#encodelua)**  
  Re-encode or remux part of the current video. Can also preserve some filters, such as "crop".

* **[equalizer](https://gist.github.com/avih/41acff712abd32e1f436235388c8b523)**  
  5-bands equalizer with colorful display.

* **[excerpt](https://github.com/lvml/mpv-plugin-excerpt)**  
  Allows you to quickly create excerpts from media files, you just have to set begin and end markers.

* **[Filenavigator](https://github.com/donmaiq/mpv-filenavigator)**  
  Navigate directories and open files from your system.

* **[find_subtitles](https://github.com/directorscut82/find_subtitles)**  
  (Down)load subtitles with subliminal.

* **[firequalizer15](https://github.com/mfcc64/mpv-scripts/blob/master/firequalizer15.lua)**  
  Linear phase 15-bands equalizer.

* **[fix_sub_timing](https://github.com/wm4/mpv-scripts/blob/master/fix-sub-timing.lua)**  
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
  Interactive subtitles for mpv, that provide instant translation for selected word. Works on Linux, macOS.

* **[last.fm scrobbler](https://github.com/l29ah/w3crapcli/blob/master/last.fm/mpv-lastfm.lua)**  
  Sends the information about playing tracks to [last.fm](http://last.fm/), see http://www.last.fm/help/faq?category=99 for more info.

* **[lua-mpris](https://github.com/dodo/lua-mpris)**  
  Adds mpris support to mpv.

* **[mark-chapter](https://github.com/thebombzen/scripts/blob/master/src/lua/markchapter.lua)**  
  Temporarily mark the current playback position as a chapter so you can seek to it later. Don't forget to edit input.conf to give it a keybinding.

* **[createchapter](https://github.com/shinchiro/mpv-createchapter)**  
  Similar as `mark-chapter` but with ability to export valid xml file.

* **[minesweeper](https://github.com/wm4/mpv-scripts#mineslua)**  
  Minesweeper game.

* **[mpv-Change-OSD-Media-Title](https://github.com/nmoorthy1/mpv-Change-OSD-Media-Title)**  
  Displays filename, percentage watched, current chapter, and number of frames dropped in the OSD media title and updates it whenever one of the values has changed.

* **[mpv_crop_script](https://github.com/TheAMM/mpv_crop_script)**  
  Take cropped screenshots directly within mpv, without the need for external dependencies.

* **[mpv_thumbnail_script](https://github.com/TheAMM/mpv_thumbnail_script)**  
  Show preview thumbnails when hovering over the seekbar, without the need for external dependencies.

* **[mpv_frame_info](https://github.com/Kagami/mpv_frame_info)**  
  Show frame info, similar to ffdshow's OSD.

* **[mpv_slicing](https://github.com/Kagami/mpv_slicing)**  
  Cut uncompressed fragments of the video.

* **[mpvcontextmenu](https://github.com/carmanaught/mpvcontextmenu)**  
  Comprehensive context-menu forked from [Tcl/Tk context menu](https://gist.github.com/avih/bee746200b5712220b8bd2f230e535de). Uses other scripts (see Requirements).

* **[mpvmenu](https://github.com/nezumisama/mpvmenu)**  
  Adds a pop-up menu to mpv, which can be bound to a key or button

* **[multi-command-if](https://github.com/SteveJobzniak/mpv-tools)**  
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

* **[osd-clock](https://github.com/blue-sky-r/mpv/blob/master/scripts/osd-clock.lua)**  
  Periodically shows OSD clock (many configurable options).

* **[pause-when-minimize](https://github.com/mpv-player/mpv/blob/master/TOOLS/lua/pause-when-minimize.lua)**  
  Pauses the player video when minimizing, and unpauses it when brought up again.

* **[peerflix-hook](https://gist.github.com/ElegantMonkey/bba287693830055a6bad90081c1ad4e2)**  
  Allows streaming of magnet links using peerflix, similar to youtube-dl.

* **[pitchcontrol](https://github.com/FichteFoll/mpv-scripts/blob/master/pitchcontrol.lua)**  
  Adjusts audio pitch in half-tone steps.

* **[Playlistmanager](https://github.com/donmaiq/Mpv-Playlistmanager)**  
  Helps with creating playlists, saving them and modifying your current playlist.

* **[progressbar](https://github.com/torque/mpv-progressbar)**  
  A minimalistic OSC replacement. It provides a small, unintrusive progress bar that persists at the bottom of the video window.

* **[quick-scale](https://github.com/SteveJobzniak/mpv-tools)**  
  Quickly scale the video player to a target size, with full control over target scale and max scale. Helps you effortlessly resize a video to fit on your desktop, or any other video dimensions you need!

* **[reload](https://github.com/4e6/mpv-reload)**  
  When an online video is stuck during buffering or got slow CDN source, restarting often helps. This script provides automatic reloading of videos that didn't have buffering progress for some time, keeping the current time position. It also adds `Ctrl+r` keybinding to reload video manually.

* **[repl](https://github.com/rossy/mpv-repl)**  
  A REPL for input commands that is displayed on the video window.

* **[save-sub-delay](https://github.com/zc62/mpv-scripts/blob/master/save-sub-delay.lua)**  
  This script saves the sub-delay quantity for each file. When next time the file is opened, sub-delay is automatically restored.

* **[seek-to](https://github.com/occivink/mpv-scripts#seek-tolua)**  
  Seek to an absolute timestamp specified via keyboard input.

* **[show-filename](https://github.com/yuukidach/mpv-scripts)**  
  Show the name of the current playing file.

* **[show-stream-title](https://github.com/blue-sky-r/mpv/blob/master/scripts/show-stream-title.lua)**  
  Show OSD stream/channel title when switching the IPTV channels from m3u playlist.

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

* **[subs2srs](https://github.com/kelciour/mpv-scripts/blob/master/subs2srs.lua)**  
  Automatically add new card in Anki with audio, picture and text.

* **[stats](https://github.com/Argon-/mpv-stats/)**  
  Display some statistics about the currently played file on-screen.

* **[streamcache](https://github.com/lvml/mpv-plugin-streamcache)**  
  Provides for more network-glitch-robust caching of live streams by adjusting replay speed.

* **[timer](https://github.com/AdamD2/mpv-timer)**  
  Allows the user to set a starting time and an ending time and see the time elapsed between those points with millisecond precision.

* **[tree-profiles](https://github.com/fbriere/mpv-scripts/blob/master/scripts/tree-profiles.lua)**  
Automatically apply profiles to certain directories or files.

* **[total_playtime](https://github.com/oltodosel/mpv-scripts/blob/master/total_playtime.lua)**  
Shows total playtime of current playlist.

* **[trueautosub](https://gist.github.com/fullmetalsheep/28c397b200a7348027d983f31a7eddfa)**  
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

* **[zones](https://github.com/wiiaboo/mpv-scripts/blob/master/zones.lua)**  
  Handles commands depending on where the mouse pointer is at, mostly for mouse wheel handling.

* **[addfile](https://github.com/devnikor/mpv-conf/blob/master/scripts/addfile.lua)**  
  (OS X) Add subtitle or audio track to playing video file

* **[simple-loader](https://github.com/fhlfibh/simple-loader)**  
  (Linux) Browse dirs and files on OSD, and launch them with mpv.  

* **[mpv-bookmarker](https://github.com/nimatrueway/mpv-bookmark-lua-script)**  
  Bookmark your favorite time on media files

* **[mpv-history](https://gist.github.com/garoto/e0eb539b210ee077c980e01fb2daef4a)**  
  Simple played media logger. Will generate a `mpvhistory.log` in the default mpv config folder (%APPDATA%/mpv/ or $HOME/.config/mpv/) in the format `[$DATE $TIME] $PATH ($?MEDIA-TITLE)`. Only tested on Windows.

If you want to write your own Lua scripts, have a look at the [documentation of mpv's Lua interface](https://mpv.io/manual/master/#lua-scripting).


## User Shaders

* **[LumaSharpenHook](https://gist.github.com/voltmtr/8b4404b4e23129b226b9e64863d3e28b)**  
  A sharpen filter similar to using Unsharp Mask in Photoshop ported from SweetFX shader pack.

* **[Adaptive Sharpen](https://gist.github.com/igv/8a77e4eb8276753b54bb94c1c50c317e)**  
  The shader tries to sharpen somewhat blurry edges the most, it avoids to sharpen near-flat areas and very sharp edges. One-pass version of a [HLSL](http://forum.doom9.org/showthread.php?t=172131) shader, that tweaked for a better compatibility with mpv. Tuned to work with opengl-hq.

* **[SSimDownscaler](https://gist.github.com/igv/36508af3ffc84410fe39761d6969be10)**  
  Perceptually based downscaler. More information is [here](https://graphics.ethz.ch/~cengizo/imageDownscaling.htm).

* **[SSimSuperRes](https://gist.github.com/igv/2364ffa6e81540f29cb7ab4c9bc05b6b)**  
  The aim of this shader is to make corrections to the image upscaled by mpv built-in scaler (removes ringing artifacts, tries to restore original sharpness, etc).

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

* **[mpv-youtube-dl-binding](https://github.com/antoniy/mpv-youtube-dl-binding)**  
  Natively play video streams in Firefox.

* **[playphrase](https://github.com/kelciour/playphrase)**  
  Search and play phrases from movies and audiobooks.

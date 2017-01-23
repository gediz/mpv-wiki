# User Scripts

Here is a list of scripts that users of mpv have published, adding functionality that is not part of the core mpv player.
Most of these scripts are **unofficial 3rd party scripts**. Anyone can add their own script by editing this wiki.


## Lua Scripts

* **[autocrop](https://github.com/mpv-player/mpv/blob/master/TOOLS/lua/autocrop.lua)**  
  Automatically crop the video by using lavfi's cropdetect filter to detect black bars.

* **[autospeed](https://github.com/kevinlekiller/mpv_scripts/blob/master/autospeed/)**  
  To adjust monitor refresh rate and video speed for almost 1:1 playback. (*nix)

* **[autospeedwin](https://raw.githubusercontent.com/kevinlekiller/mpv_scripts/master/autospeedwin/)**  
  To adjust monitor refresh rate and video speed for almost 1:1 playback. (Windows)

* **[autodeint](https://github.com/mpv-player/mpv/blob/master/TOOLS/lua/autodeint.lua)**  
  Automatically deinterlace the video by using lavfi's idet filter to detect interlaced content.

* **[auto-keep-gui-open](https://github.com/SteveJobzniak/mpv-tools/blob/master/auto-keep-gui-open.lua)**  
  Intelligently switches mpv's "keep-open" behavior based on whether you are running in video-mode or audio-only mode.

* **[autoload](https://github.com/mpv-player/mpv/blob/master/TOOLS/lua/autoload.lua)**  
  Automatically load playlist entries before and after the currently playing file, by scanning the directory.

* **[auto-profiles](https://github.com/wm4/mpv-scripts/blob/master/auto-profiles.lua)**  
  Automatically apply profiles based on predicates written as Lua expressions.

* **[autosub](https://gist.github.com/selsta/ce3fb37e775dbd15c698)**  
  Automatically download subtitles using **subliminal**.

* **[betterchapters](https://gist.github.com/Hakkin/4f978a5c87c31f7fe3ae)**  
  Loads the next or previous playlist entry if there are no more chapters in the seek direction.

* **[convert_script](https://gist.github.com/Zehkul/25ea7ae77b30af959be0)**  
  Script to quickly convert and crop videos from within mpv, with a GUI.

* **[cycle-deinterlace-pullup](https://github.com/mpv-player/mpv/blob/master/TOOLS/lua/cycle-deinterlace-pullup.lua)**  
  Cycle between deinterlacing, pullup (IVTC), and both filters off.

* **[cycle_messages](https://gist.github.com/rrooij/59f57ff5f5a952e56bbb)**  
  Cycle between custom OSD messages.

* **[cycle-video-rotate](https://github.com/SteveJobzniak/mpv-tools/blob/master/cycle-video-rotate.lua)**  
  Allows you to perform video rotation which perfectly cycles through all 360 degrees without any glitches.

* **[drc-control](https://github.com/mpv-player/mpv/blob/master/TOOLS/lua/drc-control.lua)**  
  Cycle through DRC (dynamic range compression) modes during runtime.

* **[dessubdb](https://github.com/demanuel/dessubdb/blob/master/mpv.lua)**  
  Download automatically subtitles from the thesubdb.com using [DESSubdb](https://github.com/demanuel/dessubdb).

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

* **[fpsadjust](https://github.com/haasn/gentoo-conf/blob/nanodesu/home/nand/.mpv/scripts/avail/fpsadjust.lua)**  
  Automatically adjust playback speed to synchronize the video to the display if possible (eg. by adjusting 23.976 Hz to 24 Hz for better compatibility with a 60 Hz display).
**Obsolete:** mpv now has a native display-sync option.

* **[last.fm scrobbler](https://github.com/l29ah/w3crapcli/blob/master/last.fm/mpv-lastfm.lua)**  
  Sends the information about playing tracks to [last.fm](http://last.fm/), see http://www.last.fm/help/faq?category=99 for more info.

* **[lua-mpris](https://github.com/dodo/lua-mpris)**  
  Adds mpris support to mpv.

* **[minesweeper](https://github.com/wm4/mpv-scripts#mineslua)**  
  Minesweeper game.

* **[mpv-Change-OSD-Media-Title](https://github.com/nmoorthy1/mpv-Change-OSD-Media-Title)**  
  Displays filename, percentage watched, current chapter, and number of frames dropped in the OSD media title and updates it whenever one of the values has changed.

* **[mpv_frame_info](https://github.com/Kagami/mpv_frame_info)**  
  Show frame info, similar to ffdshow's OSD.

* **[mpv_slicing](https://github.com/Kagami/mpv_slicing)**  
  Cut uncompressed fragments of the video.

* **[mpvmenu](https://github.com/nezumisama/mpvmenu)**  
  Adds a pop-up menu to mpv, which can be bound to a key or button

* **[multi-command-if](https://github.com/SteveJobzniak/mpv-tools/blob/master/multi-command-if.lua)**  
  Very powerful conditional logic and multiple action engine for your keybindings, without having to write a single line of code!

* **[myshows](https://github.com/gim-/mpv-plugin-myshows)**  
  Marks currently watched episode on MyShows website.

* **[nextfile](https://github.com/donmaiq/mpv-nextfile)**  
  Force opens next or previous file in the currently playing files folder.

* **[notify](https://github.com/rohieb/mpv-notify)**  
  Adds desktop notifications to the mpv media player, which show metadata like artist, album name and track name when the track changes.

* **[ontop-playback](https://github.com/mpv-player/mpv/blob/master/TOOLS/lua/ontop-playback.lua)**  
  Disables the ontop property when pausing, and enables it again when unpausing the video, if it was disabled.

* **[ontop-playback](https://github.com/yuzukin/mpv/blob/master/TOOLS/lua/ontop-playback.lua)**  
  Disables the ontop property when pausing, and enables it again when unpausing the video, if it was disabled. Change it only when the player is not in fullscreen to prevent screen flickering.

* **[open-file-dialog](https://github.com/rossy/mpv-open-file-dialog)**  
  (Windows) Launches a regular Windows file open dialog for loading videos.

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

* **[quick-scale](https://github.com/SteveJobzniak/mpv-tools/blob/master/quick-scale.lua)**  
  Quickly scale the video player to a target size, with full control over target scale and max scale. Helps you effortlessly resize a video to fit on your desktop, or any other video dimensions you need!

* **[reload](https://github.com/4e6/dotfiles/blob/master/.config/mpv/scripts/reload.lua)**  
  This script provides automatic reloading of videos that doesn't have buffering progress for some time while keeping the current time position. It also adds a keybinding to reload video manually.

* **[repl](https://github.com/rossy/mpv-repl)**  
  A REPL for input commands that is displayed on the video window.

* **[seek-to](https://github.com/occivink/mpv-scripts#seek-tolua)**  
  Seek to an absolute timestamp specified via keyboard input.

* **[skipchapters](https://github.com/haasn/gentoo-conf/blob/nanodesu/home/nand/.mpv/scripts/avail/skipchapters.lua)**  
  Automatically skip chapters matching a given list of regular expressions (eg. "OP" or "Opening").

* **[skiptofade](https://gist.github.com/bossen/3cfe86a6cdd61452dbb96865128fb327)**  
  Seeks forward until a black screen appears. Built to skip openings. Uses the lavfi blackdetect filter. 

* **[sopcast](https://github.com/Akemi/mpv-sopcast-hook)**  
  Adds support for sop:// urls.

* **[stats](https://github.com/Argon-/mpv-stats/)**  
  Display some statistics about the currently played file on-screen.

* **[streamcache](https://github.com/lvml/mpv-plugin-streamcache)**  
  Provides for more network-glitch-robust caching of live streams by adjusting replay speed.

* **[unseen-playlistmaker](https://github.com/donmaiq/unseen-playlistmaker)**  
  Keeps track of watched files locally, and creates playlists of unwatched files.

* **[vo_battery](https://gist.github.com/selsta/9ac023688885053d42ca)**  
  (OS X) Choose the VO based on if the laptop is on battery or not.

* **[vo_battery](https://gist.github.com/ElegantMonkey/04924e899648e84f2e18)**  
  (Linux) Choose the VO based on if the laptop is on battery or not.

* **[waifu2x](https://github.com/donmaiq/mpv-waifu2x)**  
  Take screenshots and convert images with waifu2x.

* **[xrandr](https://github.com/lvml/mpv-plugin-xrandr)**  
  Automatically sets the display refresh rate to the one best suitable for the video played

* **[zones](https://github.com/wiiaboo/mpv-scripts/blob/master/zones.lua)**  
  Handles commands depending on where the mouse pointer is at, mostly for mouse wheel handling.

* **[addfile](https://github.com/devnikor/mpv-conf/blob/master/scripts/addfile.lua)**  
  (OS X) Add subtitle or audio track to playing video file

* **[simple-loader](https://github.com/fhlfibh/simple-loader)**  
  (Linux) Browse dirs and files on OSD, and launch them with mpv.  

If you want to write your own Lua scripts, have a look at the [documentation of mpv's Lua interface](https://mpv.io/manual/master/#lua-scripting).


## Pixel Shaders

* **[LumaSharpenHook](https://gist.github.com/voltmtr/8b4404b4e23129b226b9e64863d3e28b)**  
  A sharpen filter similar to using Unsharp Mask in Photoshop ported from SweetFX shader pack.

* **[FineSharp](https://gist.github.com/igv/a9a21ad1f6dd7d0b4452)**  
  FineSharp by Didée converted from mpc-hc shaders. Tuned to work with opengl-hq. [More info](http://forum.doom9.org/showthread.php?t=171346)

* **[Adaptive Sharpen](https://gist.github.com/igv/4792d0abab41d436ac1a51bb171f8c2f)**  
  A two-pass sharpen filter to sharpen medium sharp edges the most. Ported from a [HLSL](http://forum.doom9.org/showthread.php?t=172131) shader. Tuned to work with opengl-hq.

* **[One-Pass Adaptive Sharpen](https://gist.github.com/igv/8a77e4eb8276753b54bb94c1c50c317e)**  
  One-pass version of adaptive sharpen shader. Has built-in anti-ringing filter.

* **[KrigBilateral](https://gist.github.com/igv/a015fc885d5c22e6891820ad89555637)**  
  Chroma scaler that uses luma information for high quality upscaling.

* **[SSimSuperRes](https://gist.github.com/igv/2364ffa6e81540f29cb7ab4c9bc05b6b)**  
  The aim of this shader is to make corrections to the upscaled image. Works with regular scalers only, not prescalers.

* **[Noise](https://github.com/haasn/gentoo-conf/blob/nanodesu/home/nand/.mpv/shaders/noise.glsl)**  
  Adds a tunable amount of grayscale noise to the output.

* **[Antiringing](https://github.com/haasn/gentoo-conf/blob/nanodesu/home/nand/.mpv/shaders/antiring.hook)**  
  This is basically the equivalent (with some caveats) of mpv's built-in antiringing shader.

* **[SuperXBR and Nnedi3](https://github.com/bjin/mpv-prescalers/tree/master)**  
  User shaders for prescaling. These shaders should cover most functionality that `prescale-luma=` used to provide.

## VapourSynth Scripts

* **[mvtools](https://github.com/haasn/gentoo-conf/blob/nanodesu/home/nand/.mpv/filters/mvtools.vpy)**  
  Use [MVTools](https://github.com/dubhater/vapoursynth-mvtools)'s BlockFPS function to perform motion interpolation on the video in realtime.

* **[nnedi3](https://github.com/haasn/gentoo-conf/blob/nanodesu/home/nand/.mpv/filters/nnedi3.vpy)**  
  Use [NNEDI3](https://github.com/dubhater/vapoursynth-nnedi3) to double the resolution of the video. This always performs a single doubling. Note that the vapoursynth-nnedi3 filter is so slow that this practically can't be used in realtime, so it's not much use in practice. 

* **[flash3kyuu](https://github.com/haasn/gentoo-conf/blob/nanodesu/home/nand/.mpv/filters/flash3kyuu.vpy)**  
  Use [flash3kyuu](https://github.com/SAPikachu/flash3kyuu_deband) to deband the video, with reasonable (mildly grainy) default settings. 
**Obsolete:** mpv now ships with a similar debanding filter as shader.

## Other

* **[mpv-youtube-dl-binding](https://github.com/antoniy/mpv-youtube-dl-binding)**  
  Natively play video streams in Firefox.
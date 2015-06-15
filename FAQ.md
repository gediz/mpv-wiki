### Does mpv have an official GUI?

No. But there is the OSC (on-screen-controller), which lets you control playback with the mouse. Requires mpv to be compiled with Lua support.

### I can't see the OSC/OSD/GUI!

The OSC requires Lua support. Install Lua (including development headers) and rebuild mpv.
If you didn't build mpv yourself, ask the packager to enable Lua.

Also note that the OSC is invisible by default, but it should appear once you move the mouse over the mpv window.

### If I click mpv, nothing happens.

mpv is a command line program and doesn't provide an actual GUI. You need to start it with a media file. On Windows, you can create a file association with the ``Open with…`` context menu. Also, if you start ``mpv.exe`` from ``explorer.exe``, it will enter [pseudo-gui mode](http://mpv.io/manual/master/#pseudo-gui-mode). For Linux, a ``mpv.desktop`` file is provided.

You can also start mpv with ``mpv --profile=pseudo-gui``. You play files by dropping them on the window.

### Is FFmpeg or Libav preferred for use with mpv?

Generally FFmpeg, simply because it has more features.
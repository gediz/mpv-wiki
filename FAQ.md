### Does mpv have an official GUI?

No. But there is the OSC (on-screen-controller), which lets you control playback with the mouse. Requires mpv to be compiled with Lua support.

### Tearing

[Tearing](https://en.wikipedia.org/wiki/Screen_tearing) is a very annoying artifact that makes it look like the video has a horizontal line across the video. The video isn't properly joining on that line. The line can be fixed or moving. Sometimes it's not a line, but a bunch of blocks. It can be unnoticeable if there is no movement, but very apparent if the camera moves e.g. at low speed.

Tearing is generally not something a video player can do anything about. It depends on the hardware, drivers, the video output selected in mpv (VO), and possibly the desktop environment / compositor.

Changing the compositor settings can sometimes help with tearing.

* Windows/OSX

  Tearing should never happen.
* Nvidia

 Nvidia should generally not tear. Sometimes, it tears in windowed mode, but not in fullscreen (solution unknown). There are additional problems on multimonitor systems. 
    * Try enabling ``ForceFullCompositionPipeline``.
    * Try with and without a compositor.
    * Try ``--vo=vdpau``.

* Intel

  Intel tears out of the box.
    * Try enabling SNA and the ``TearFree`` option.

      Unfortunately, this can cause stability issues - GL applications sometimes randomly crash. Somewhere, there's a claim that adding ``i915.semaphores=1`` to your kernel parameters fixes the crashes.
    * Try disabling SNA by using UXA (on older hardware).
    * Try ``--vo=xv:adaptor=N``, and try 0 or 1 for ``N``. This may fix tearing if the other methods fail, but keep in mind that using Xv with mpv is strongly discouraged.
    * Try ``--vo=vaapi``. Although this is Intel's native video output method, it seems to fix tearing only very rarely.

### I can't see the OSC/OSD/GUI!

The OSC requires Lua support. Install Lua (including development headers) and rebuild mpv.
If you didn't build mpv yourself, ask the packager to enable Lua.

Also note that the OSC is invisible by default, but it should appear once you move the mouse over the mpv window.

### If I click mpv, nothing happens.

mpv is a command line program and doesn't provide an actual GUI. You need to start it with a media file. On Windows, you can create a file association with the ``Open with…`` context menu. Also, if you start ``mpv.exe`` from ``explorer.exe``, it will enter [pseudo-gui mode](http://mpv.io/manual/master/#pseudo-gui-mode). For Linux, a ``mpv.desktop`` file is provided.

You can also start mpv with ``mpv --profile=pseudo-gui``. You play files by dropping them on the window.

### Can I set volume over 100%?

On some systems, 100% is the maximum. You can put ``softvol=yes`` to force mpv's own volume filter. Then the ``softvol-max`` option controls the maximum. It's 130 by default.

Also consider using ``af=drc``, which helps especially with crappy speakers.

Note that in older versions of mpv, a volume of ``100`` always meant maximum, even if the maximum mapped to a linear gain factor over ``1.0``.

### Is FFmpeg or Libav preferred for use with mpv?

Generally FFmpeg, simply because it has more features.
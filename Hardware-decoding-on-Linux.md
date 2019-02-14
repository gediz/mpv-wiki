# Intel and AMD
With recent `mesa` and `ffmpeg`, both cards are supported by VA-API through `libva>=2.1`. Install `libva-intel-driver` and `libva-mesa-driver`. Make sure that your system does not have the following packages, 
1. `libva-vdpau`
2. `libva-va-gl`
3. `libvdpau-va-gl`

## Intel
You need to use `hwdec=vaapi` and other options can be configured according to your GPU. To make it permanent, add it to `~/.config/mpv/mpv.conf`.

Intel HD graphics need `i965-va-driver` installed to work properly (at least on *debian stretch*).

## AMD
Since dedicated graphics are going to be used, some environment variables are specified to instruct the driver to
load specific modules.
```sh
DRI_PRIME=1            # for laptops with switchable graphics
LIBVA_DRIVER_NAME=r600 # value depends on the driver, check /usr/lib/dri for possible options
```
In mpv, you specify `hwdec=vaapi` and `gpu-context=x11egl` for Xorg.

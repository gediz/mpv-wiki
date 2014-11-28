# Downscaling Option Evaluation

## Why are downscaling options relevant?

Scaling moving pictures from a higher resolution to a lower resolution can yield very differently looking results, depending on the scaling method and its parametrization. The smaller you scale the image, the more likely may experience awful looking aliasing/ringing/blurring artefacts when not using a high quality downscaling method.

mpv provides a lot of scaling options, you can find those that are associated with certain video output drivers documented [here](https://github.com/mpv-player/mpv/blob/master/DOCS/man/vo.rst).

## Downscaling options with -vo opengl

Here are some results evaluating downscaling options available with the opengl video driver, tested for visual quality, GPU usage and power consumption.

Regarding optimal visual quality, best results were achieved with

`-vo opengl:lscale-down=mitchell:lparam1=0.3:lparam2=0.3:cscale-down=mitchell:cparam1=0.3:cparam2=0.3:scaler-resizes-only:fancy-downscaling:dither-depth=auto:fbo-format=rgba16`

The options `lparam1=0.3:lparam2=0.3` and `cparam1=0.3:cparam2=0.3` are default for the Mitchell-Netravali filter method, anyway, `scaler-resizes-only` and `dither-depth=auto` are sane defaults that shall not be further discussed in the scope of this page.

The most determining options for visual quality are `lscale-down=mitchell` to choose the method for downscaling, `fancy-downscaling` to use a larger convolution matrix, and to a lesser degree `fbo-format=rgba16`, which sets a destination pixel format for the scaler that (unlike e.g. YUV 4:2:0 or any 8-bit-per-pixel format) allows to retain as much luminance and chroma information as there is available.

`lscale-down=mitchell` and `fancy-downscaling` both individually contribute very visible to the quality of the down-scaled image (try best with sharp, high-resolution, detail-rich video material), but most convincing visual results are achieved only when using both options together. (It was said that `fancy-downscaling` might not work well with non-1:1-aspect pixels, not tested yet.)

Using these 3 options comes at the price of higher computational effort. When using a GPU hardware, this effort will be done in the GPU and not show up as additional CPU usage. If you have to use a CPU or a weak GPU for scaling, you might stretch the limits of your system, so try leaving away one or the other option if your replay is not smooth with all of them.

Measurements on the GPU usage and power consumption of the three most relevant options were done on an Intel Core i7-3517U CPU built into an Asus UX32VD laptop, using 4k video material and `-hwdec vaapi` to decode the h.264 material in hardware. GPU usage was measured using [intel_gpu_top](http://cgit.freedesktop.org/xorg/app/intel-gpu-tools/), power consumption was measured using [powertop](https://01.org/powertop/).

intel_gpu_top reports a percentage value named "render busy", to this value the options contributed:

* lscale=mitchell: 14%
* fancy-downscaling: 13%
* fbo-format=rgba16: 7%

(The CPU consumption while playing was at ~8% and did not change with the scaling options.)

Baseline power consumption while laptop was not playing anything: 6.49 W.
Power consumption while mpv was playing 4k video file with all of `lscale-down=mitchell:fancy-downscaling:fbo-format=rgba16`: 23.2 W
Power consumption while mpv was playing 4k video file without these three options: 19.6 W









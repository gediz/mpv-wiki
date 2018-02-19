# Use `vo_gpu`

There is some confusion with regards to the different VOs that mpv has to offer. Unless you ***really*** know what you're doing, **you should be using `vo_gpu`**.

## But I want hardware decoding!

And you can get that by just setting `hwdec`. The `vo_vaapi` and `vo_vdpau` video outputs are separate parts of the vaapi and vdpau APIs which don't tie into hardware decoding at all. They should not be used.

## But `vo_gpu` is slow for me!

There's a couple of reasons why that could be, ranging from a weak GPU to broken drivers that fall back to software rendering, but there is a good reason as to why `vo_gpu` requires more power than some of the "dumber" video outputs.

`vo_gpu` uses your GPU's shader pipeline\* to do the video rendering itself, this way mpv can control the scaling, dithering and other things in detail. With other VOs such as `vo_vaapi` and `vo_vdpau`, mpv just feeds data into what is essentially a black box. It has very little control over how the video is rendered, which means none of the `gpu-hq` settings apply, or any of mpv's gpu video rendering options for that matter. Sure, this means that the video rendering is potentially faster, but only because it is being done in a very simplistic and probably low-quality manner.

\* *A quick note on what a shader pipeline is: During the 90s and early 2000s, GPUs could only render with a fixed pipeline. This means you threw data at the graphics API, and got pixel data as a result. You had very little control over how that data was actually processed apart from a few parameters you could tweak. Then, around 5 years into the new millennium, there was a quantum leap in graphics processors and graphics APIs: programmable shader pipelines! Suddenly, the pipeline was divided up into several stages, of which some could be reprogrammed in special shading language code. This meant applications didn't just have control over what data they fed into the graphics API, but also how that data was to be processed. mpv's `vo_gpu` output makes heavy use of this programmable shader pipeline.*

## But `vo_gpu` is broken for me!

This can happen if your drivers are broken or if your GPU is a potato from the Jurassic period. Check that you even get any OpenGL acceleration at all; on Linux with X11 you could do this with `glxinfo`. If it spits out an error or contains ominous signs like the word "llvmpipe", chances are your driver is broken in some way.

If you have recently upgraded your version of Mesa, especially on a rolling-release distribution, try rebooting your computer first to see if that fixes your issues. Mesa updates can occasionally break OpenGL acceleration until the system is restarted.

## But all I have is `vo_opengl`!

Stop using an outdated version of mpv.
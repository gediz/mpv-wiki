The goal is to make the directory structure somewhat more logical, cleaner, and making things easier to find.

* libaf/ -> af/
* libao2/ -> ao/
* libmpdemux/ -> demux/
* libvo/ -> vo/

libmpcodecs is split into multiple toplevel directories:

* vf* -> vf/
* dec_video.*, vd* -> video/
* dec_audio.*, ad* -> audio/
* img_format*, mp_image* -> vf/ (Maybe. Like af/format.h defines audio formats, vf/ contains files that define the image format.)

After that, libmpcodecs should be empty.

From pigoz:
As I mentioned on IRC: I think a /core directory containing files in the root and the following directories /input, /timeline would be beneficial.

I'd also like this kind of directory structure

```
 /
 |- audio/
  |- format.h
  |- decoders/
  |- demuxers/
  |- filters/
  |- outputs/
 |- core/
  |- mplayer.c
 ....
  |- input/
  |- timeline/
 |- osdep/
 |- stream/
 |- subtitle/
 |- video/
  |- format.h
  |- decoders/
  |- demuxers/
  |- filters/
  |- outputs/
 |- README
 |- LICENSE
 |- Makefile
```
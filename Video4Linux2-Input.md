With the removal of the old `tv://` input, the now preferred method of playing back video from capture devices such as webcams or capture cards is the `av://` input protocol:

```
mpv av://v4l2:/dev/video0 --profile=low-latency
```

The `--untimed` option can be added as a hack to show frames as fast as the capture device presents them, which can help reduce latency further.

Due to Video4Linux2 being quite stateful, mpv will pick whatever input format, resolution and framerate the device just happened to be configured to use at the time, which can be suboptimal.

# Setting The Input Format

Video4Linux2 devices can expose both raw uncompressed video formats or compressed video formats, which support different maximum resolutions and framerates as uncompressed formats are often bottlenecked by USB 2.0 bandwidth limitations.

To find the specific formats, resolutions and framerates a device (in this example `/dev/video2`) supports, one can use `v4l2-ctl --list-formats-ext -d /dev/video2`. If the `-d` option is omitted, `/dev/video0` is chosen by default.

For mpv to then set this input format, the right option needs to be passed to libavformat through `--demuxer-lavf-o`:

```
mpv --demuxer-lavf-o=video_size=1280x720:input_format=mjpeg av://v4l2:/dev/video0 --profile=low-latency
```

Multiple options can be set separated by a colon (`:`), with the list of possible options for Video4Linux2 being listed on [ffmpeg's devices documentation](https://ffmpeg.org/ffmpeg-devices.html#Options-18). The important ones are:
* `video_size` - the resolution to pick
* `input_format` - the format to pick, usually one of `mjpeg`, `h264` (if the camera supports it) or `rawvideo`
* `framerate` - the framerate to set the camera to

Be aware that for both `video_size` and `framerate`, setting a combination that the camera does not support (especially when choosing a `input_format` that does not allow for this combination) will just silently pick whatever works.

# Adding An Audio Input

Your capture device probably also exposes an audio input. mpv can be made to use this input in conjunction with the video, but syncing the two up is left up to you.

To list the available audio inputs on a PulseAudio system, use `pactl list sources`.

You can then use the name of your desired input with mpv's `--audio-file` option; in this example, the ffmpeg libraries mpv is built against must have been compiled with `--enable-libpulse` as the `pulse` input device won't exist otherwise:

```
mpv av://v4l2:/dev/video0 --profile=low-latency --audio-file av://pulse:name-of-your-device
```

where `name-of-your-device` should be the identifier after the `Name:` line of your pactl output.

The audio sync can be adjusted with `Ctrl +` and `Ctrl -` during playback, or at the start with the `--audio-delay` option.

An untested suggestion for achieving perfect sync every time is to set the Video4Linux2 input to use wallclock time with `--demuxer-lavf-o=timestamps=abs`. In theory, this should make sure that both the PulseAudio and Video4Linux2 inputs use the same timestamp basis.
mpv 0.8 introduces a breaking change for ALSA users: Instead of a stereo configuration, it uses the media file’s channel layout by default. In addition, a hack in the ALSA output that automatically selected audio devices like `surround51` based on the requested channel layout was removed in favor of a newer channel mapping API.

The automatic device selection may have been convenient for some users, but these devices are typically set up for exclusive access so they do not allow mixing multiple streams, which makes it impossible to have multiple applications playing audio while they are in use.

With that removed, mpv is limited to the capabilities of the `default` device unless the user specifies a different one. This is a problem because distributions generally do not ship ALSA with a configuration that allows playing anything with more than two channels on the default device. But of course, manually setting a device every time you want to play something with a channel map that your default device can’t handle is not acceptable.

Hence, the solution is to change your ALSA configuration so that it *does* allow multiple streams of different channel configurations and upmixes on demand, thus fixing both problems.

**For this to work, you need the `upmix` plugin for ALSA, which distributions typically include in an `alsa-plugins` or `libasound2-plugins` package (you should have this installed anyway since otherwise the default ALSA resampler will sound terrible).** Remember to install the 32-bit version too if you are running 32-bit applications on a 64-bit system!

Also, the configuration below will not work with sound cards that the kernel exposes as several stereo subdevices instead of one true multichannel card. This restriction applies e.g. to everything based on the EMU10K1 chip.

You can use this default device in your `~/.asoundrc` or the system-wide `/etc/asound.conf`:

```
pcm.!default {
    type asym # combined playback and capture

    playback.pcm {
        type plug # format conversion

        slave.pcm {
            type upmix # on-demand upmixing

            slave.pcm {
                type dmix # multi-stream mixing
                ipc_key 4897

                slave {
                    pcm hw
                    channels 6 # adjust as necessary (e.g. 8 for 7.1 audio)

                    # MAY be necessary to avoid buffer underruns/audio skipping
                    # YMMV, remove or adjust values as you see fit
                    period_time 0
                    period_size 1024 # double if you notice increased CPU load or crackling
                                     # halve if you like lower latency
                                     # (e.g. when adjusting volume with softvol enabled)
                    buffer_time 0
                    buffer_size 8192 # some applications do not like smaller buffers
                }
            }
        }
    }

    capture.pcm {
        type dsnoop
        ipc_key 7974
        slave.pcm hw
    }
}
```

Once you have saved the file, simply restart any applications using ALSA to reload the settings.

If you get the following error while trying to use it
```
ALSA lib pcm_direct.c:955:(snd1_pcm_direct_initialize_slave) unable to set buffer size
```
you have to adjust the buffer sizes. Just commenting/removing all buffer options may help too, potentially at the risk of higher latency. The exact settings that will work depend on your hardware and driver quality.
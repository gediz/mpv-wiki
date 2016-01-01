Support for LIRC has been removed in mpv 0.9.0. The new way to use such devices is through evdev. This means the devices will emit normal X11 key events. You should be seeing these key press events if you start ``xev`` (make sure ``xev`` is focused). This might require additional configuration with ``ir-keytable``.

Likewise, if you use them in mpv, mpv should complain about an unmapped key. You can use the printed key name or code and add a binding to input.conf. You can also see all key events mpv receives with ``mpv --input-test --force-window --idle``.

Some IR devices (in particular very old ones) might not work.

If you're using [lirc](http://lirc.org/), `irxevent` can be useful in routing appropriate commands to mpv:

```
begin
  prog = irxevent
  button = Play
  config = Key space mpv
end

begin
  prog = irxevent
  button = Volume+
  config = Key 0 mpv
  repeat = 1
  delay = 1
end
```

Alternatively, and since mpv cannot natively bind global key bindings, if you really need to control mpv while mpv is not focused, consider writing a script that controls mpv through a [FIFO](http://mpv.io/manual/master/#options-input-file) or [JSON IPC](http://mpv.io/manual/master/#json-ipc).
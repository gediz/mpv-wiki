Currently, there are two kind of bindings:

1. Internal: can be used from inside of mpv only.
2. External: can't control the mpv command line player, but can be used to implement new applications that use libmpv as backend for video playback.

Both of them use the libmpv client API: https://github.com/mpv-player/mpv/blob/master/libmpv/client.h

### Internal bindings

- Lua: https://mpv.io/manual/master/#lua-scripting
- JavaScript: https://mpv.io/manual/master/#javascript

### External bindings

- Python: https://github.com/jaseg/python-mpv
- Python (another one): https://github.com/marcan/pympv
- Ruby: https://github.com/woodruffw/ruby-mpv
- JavaScript: https://github.com/rcombs/node-mpv
- JavaScript (PPAPI): https://github.com/Kagami/mpv.js
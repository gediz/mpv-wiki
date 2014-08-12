Currently, there are two kind of bindings:

1. Internal: can be used from inside of mpv only.
2. External: can't control the mpv command line player, but can be used to implement a new applications that use libmpv as backend for video playback.

Both of them use the libmpv client API: https://github.com/mpv-player/mpv/blob/master/libmpv/client.h

### Internal bindings

- Lua: https://github.com/mpv-player/mpv/blob/master/DOCS/man/lua.rst

### External bindings

- Python: https://github.com/andre-d/pympv
- Python (another one): https://github.com/jaseg/python-mpv

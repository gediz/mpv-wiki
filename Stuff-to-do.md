Here are some tasks that need to be done in mpv, require some effort, are not already grabbed by anyone, and which are thought to be doable by anyone without requiring too much mpv-specific knowledge.

- Think of a way how to improve security by restricting unintended "redirects" due to playlist files and similar things. For example, a playlist on disk could contain remote links, or a playlist retrieved from http could reference local files. Since HLS, a popular streaming protocol, uses "playlists", streams loading other references must be enabled by default. We should come up with a security concept that mitigates these problems.

- Replace Xlib usage with XCB. (Basically writing a new backend for X11, based on XCB instead of Xlib. Preferably without using the old code, so it can be LGPL.)

- Write a new LGPL ALSA audio output. (Without using the old ao_alsa.c code.)

- Support keyboard play/pause buttons and MCE remotes on Windows. This will probably require global hotkeys to be set up. Needs a lot of different hardware for testing since these seem to work differently with every device.

- Make ytdl lua wrapper more sophisticated: async loading of playlists, loading of both playlist and video if an URL has both, preloading of ytdl videos.

- Make ffmpeg load/expose embedded ICC profiles in images, and hook this up to video/out/opengl/lcms.c

- Figure out a way to get rid of redundant passes inside vo_opengl in a clean way, ideally kill dumb mode

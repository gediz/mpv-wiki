Here are some tasks that need to be done in mpv, require some effort, are not already grabbed by anyone, and which are thought to be doable by anyone without requiring too much mpv-specific knowledge.

- Replace Xlib usage with XCB. (Basically writing a new backend for X11, based on XCB instead of Xlib. Preferably without using the old code, so it can be LGPL.)

- Write a new LGPL ALSA audio output. (Without using the old ao_alsa.c code.)

- Support keyboard play/pause buttons and MCE remotes on Windows. This will probably require global hotkeys to be set up. Needs a lot of different hardware for testing since these seem to work differently with every device.

- Make ytdl lua wrapper more sophisticated: async loading of playlists, loading of both playlist and video if an URL has both, preloading of ytdl videos.

- Help with LGPL relicensing. (Stuff like talking to people, or finding out who else has to be asked or not asked.)
Here are some tasks that need to be done in mpv, require some effort, are not already grabbed by anyone, and which are thought to be doable by anyone without requiring too much mpv-specific knowledge.

- We need a community manager. This person would reduce the need for developers to deal with day to day operations, such as communicating with users, adjusting the website and documentation, triaging bugs and feature requests, and other non-developer tasks.

- Think of a way how to improve security by restricting unintended "redirects" due to playlist files and similar things. For example, a playlist on disk could contain remote links, or a playlist retrieved from http could reference local files. Since HLS, a popular streaming protocol, uses "playlists", streams loading other references must be enabled by default. We should come up with a security concept that mitigates these problems.

- Replace Xlib usage with XCB. (Basically writing a new backend for X11, based on XCB instead of Xlib. Preferably without using the old code, so it can be LGPL.)

- Write a new LGPL ALSA audio output. (Without using the old ao_alsa.c code.)

- Make ytdl lua wrapper more sophisticated: async loading of playlists, loading of both playlist and video if an URL has both, preloading of ytdl videos.

- Export src_rect and dst_rect from the VO via property (perhaps read-writable?)

- Make the gamma curve definitions and tone mapping functions in video_shaders.c work for full-range values, and remove the force clip to [0,1]

- We need a maintainer for the OSC (the "UI" that appears as overlay over the video).
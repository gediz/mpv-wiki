If you're new to the project, and want to help, here are some suggestions what to work on. You're also welcome to come up with your own ideas.

- We need a community manager. This person would reduce the need for developers to deal with day to day operations, such as communicating with users, adjusting the website and documentation, triaging bugs and feature requests, and other non-developer tasks.

- Come up with a way how mpv user scripts (also shaders etc.) can be packaged and updated in a reasonable way. The goal is having a way to automatically manage these scripts.

- Write a help overlay script, which shows mapped key bindings and their meaning. (This would require new mpv API to retrieve current key bindings and so on, which you could implement yourself, or which could be added by other developers.)

- Think of a way how to improve security by restricting unintended "redirects" due to playlist files and similar things. For example, a playlist on disk could contain remote links, or a playlist retrieved from http could reference local files. Since HLS, a popular streaming protocol, uses "playlists", streams loading other references must be enabled by default. We should come up with a security concept that mitigates these problems.

- Replace Xlib usage with XCB. (Basically writing a new backend for X11, based on XCB instead of Xlib. Preferably without using the old code, so it can be LGPL.)

- Make ytdl lua wrapper more sophisticated: async loading of playlists, loading of both playlist and video if an URL has both, preloading of ytdl videos.

- Export src_rect and dst_rect from the VO via property (perhaps read-writable?)

- Make the gamma curve definitions and tone mapping functions in video_shaders.c work for full-range values, and remove the force clip to [0,1]

- Introduce consistency in our option naming. Reorder the manpage to make options easier to find.

- We need a maintainer for the OSC (the "UI" that appears as overlay over the video).

- Convert the libmpv documentation from in-place doxygen to external documentation (the way vapoursynth does it might be a good idea).

For all of these you should ask on #mpv-devel for help and guidance.
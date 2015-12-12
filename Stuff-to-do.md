Here are some tasks that need to be done in mpv, require some effort, are not already grabbed by anyone, and which are thought to be doable by anyone without requiring too much mpv-specific knowledge.

- Replace Xlib usage with XCB. Since GLX requires Xlib, and is currently still required for most uses of OpenGL, the value of doing this is unclear.

- Implement JSON IPC for Windows. This will require splitting input/ipc.c into platform-specific and platform-independent parts. The preferred transport for this would be Windows named pipes, since they seem to be analogous to Unix domain sockets. Qt's QLocalSocket uses named pipes on Windows and Unix domain sockets on Linux, so this would allow cross-platform IPC clients to be written in Qt.

- Support keyboard play/pause buttons and MCE remotes on Windows. This will probably require global hotkeys to be set up. Needs a lot of different hardware for testing since these seem to work differently with every device.
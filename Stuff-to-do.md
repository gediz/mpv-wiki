Here are some tasks that need to be done in mpv, require some effort, are not already grabbed by anyone, and which are thought to be doable by anyone without requiring too much mpv-specific knowledge.

- Implement a Windows OpenGL backend that uses Direct3D interop. This would allow us to use Direct3D for windowing, which is much more flexible than the WGL API. The WGL API is essentially left to bitrot by Microsoft. D3D gives you explicit control over many aspects of interaction with windowing, frame presentation, the compositor, and other things. It would use this extension: https://www.opengl.org/registry/specs/NV/DX_interop.txt Essentially, code using the interop would be added as a new backend alongside ``video/out/opengl/w32.c``.
  - A working proof-of-concept that uses D3D9 interop is here: https://github.com/rossy/mpv/tree/gl-dxinterop

- Replace Xlib usage with XCB. Since GLX requires Xlib, and is currently still required for most uses of OpenGL, the value of doing this is unclear.

- Implement JSON IPC for Windows. This will require splitting input/ipc.c into platform-specific and platform-independent parts. The preferred transport for this would be Windows named pipes, since they seem to be analogous to Unix domain sockets. Qt's QLocalSocket uses named pipes on Windows and Unix domain sockets on Linux, so this would allow cross-platform IPC clients to be written in Qt.

- Support keyboard play/pause buttons and MCE remotes on Windows. This will probably require global hotkeys to be set up. Needs a lot of different hardware for testing since these seem to work differently with every device.
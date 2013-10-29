Note down stuff when I am currently not at home (like work) to not forget it.

### Minor Bugs:
- **[fixed]** If you resize furiously the video aspect does not match the window aspect and size, but after releasing the grap it adjusts itself.
- **[fixed]** If you change between fullscreen and windowed mode fast enough, the previous size gets overwritten
- Left Shift Modifier warning. No Idea where this one comes from.
- Flickers when resizing SHM backend. Requires full redraw before attaching.
- **[fixed]** [vo/wayland/wayland] logging from wayland_common.h

### Short Term:
- **[done]** Remove left overs from the big epoll removal (like ARRAY_LENGTH).
- **[done]** Refactor keyboard_handle_keyboard
- **[done]** Use set_user_data for `wl_output` to map the corresponding `vo_wayland_output` to it. With this we can get rid of the iteration over all outputs in output_handle_mode.
- **[done]** Evaluate if there is a need for set_opaque with OpenGL and If we get better performance. **Not necessary**
- **[done]** Use a callback for resizing instead of a scheduling event to get more predictable resizing.
- **[done]** Make a separate configure check for EGL and SHM rendering.
- **[done]** Restructure the format table to to have an addition alpha field for the corresponding 
             alpha format. Also make it const and use a linked list to save the supported formats.
- **[done]** Remove move by dragging the surface ~~(this might interfere with the OSC)~~ (no problems)
- **[done]** Make use of opaque regions for opaque formats to give the compositor hints to optimize the drawing behavior.

### Long Term:
- Add Client Side Decorations in case mpv runs under a compositor which does not have Server Side Decorations (like weston). **Depends on:** Subsurface protocol
- Multithreading: The current polling solution should already be threadsafe (theoretically)
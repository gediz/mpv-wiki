The following document is supposed to list all the constraints that must be respected to make mplayer2 a "good" Cocoa application. This combined with a similar document for windows should give us an idea about what can be changed.

## Pills of Objective-C

This is to make some sense of the Apple docs that I will link.

Classes can respond to messages/selectors/methods (they are all synonyms). Objective-C messages support named parameters.

For example, this declaration:
`- (void)setContentSize:(NSSize)newSize keepCentered:(BOOL)keepCentered;`

Would roughly be like this in a JAVA like language (which only supports positional parameters):
`void setContentSize(NSSize newSize, BOOL keepCentered);`

And you send the message to the pointer to and instance like this:
`[instance setContentSize:NSMakeSize(50,50) keepCentered:YES];`

## Constraints

1. Threading: Most of Cocoa UI, Event loop and Application classes are NOT thread safe and are supposed to run in the main thread of the application. Moving them out the main thread requires opening a connection to the window server manually: that is something in his right mind no one would do since it would be brittle and maintenance hell. 

2. Event Loop: Cocoa as it's own event loop. In the Cocoa world it is called `NSRunLoop`. You can generally live without knowing too much about it since the primary RunLoop is managed by a class called NSApplication. You just call `[NSApp run]` and it does it's thing (async listens for events and event sources, fire timers, updates UI etc) (NSApp is a singleton instance of NSApplication). Of course you need to be a good citizen and never block the event loop and perform expensive operations in secondary threads.

   A fun side note is there can be secondary RunLoops that are used mainly for mouse tracking operations such as navigating menus or resizing a window with the mouse. These nested RunLoops can be made aware of timers and event sources too, so this isn't really a problem if you follow "the Cocoa way". Why this is currently problematic is explained in point 5.

   File Descriptors cannot be event sources for the NSRunLoop so if you want to do async polling on them you must do so in a separate thread. mplayer2 does this in: [`osdep/cocoa_events.m`](https://github.com/wm4/mplayer2/blob/master/osdep/cocoa_events.m)

3. File open events: non terminal applications on OSX do no receive files in the argv. That is because you couldn't deal with new file opens with a process that is already running (on OSX you generally get only one instance of each application and can open several documents with it). So in the argv you get something like `--psn-numbers-numbers` when you open files from the finder. You can actually deal with the file open events by implementing some NSApplication callback methods. This is all taken care of in the [`osdep/macosx_finder_args.m`](https://github.com/wm4/mplayer2/blob/master/osdep/macosx_finder_args.m) file.

4. Rendering OpenGL stuff. You are not supposed to render directly when you want to like mplayer2 currently does. Rendering should be done in the implementation of the `drawRect:` method of a NSOpenGLView subclass.
`drawRect:` is called automatically by the framework code some time near the the monitor refresh if the view  was flagged to need a refresh by calling `[view setNeedsDisplay:YES]`. Another more modern option is using the DisplayLink functionality from CoreVideo. CoreVideo will start a high priority thread that calls a callback slightly before the "beam". In both cases you are supposed to dequeue a frame for the current time (producer-consumer style) and just display it, if the frame is the same as before you just return nothing from the shared resource and do nothing in the drawRect method so that you keep showing the current frame. You are not supposed to do costly operation in here (i.e.: actually performing the decode on the fly). More info on driving OpenGL views [here](http://developer.apple.com/library/mac/#qa/qa1385/_index.html).

5. More on the event loop: mplayer2 currently manually dequeues Cocoa events in `vo_cocoa_check_events` by calling:

   ```objc
   event = [NSApp nextEventMatchingMask:NSAnyEventMask untilDate:nil
                  inMode:NSEventTrackingRunLoopMode dequeue:YES];
   ```

   It then sends the event to NSApplication with `[NSApp sendEvent:event];`. NSApp is in charge to dispatching the event to the NSWindow, and NSWindow could potentially dispatch the event to NSViews instances it contains. The problem is when we have an event that is the start of a tracking operation (i.e.: menu navigation, window resize with mouse), `sendEvent:` defined in NSApp calls `[window sendEvent:event];`, and the window instance blocks the current function by creating a secondary RunLoop for the mouse tracking operation. When you release the mouse the secondary RunLoop stops and execution goes on. The problem is this blocks `vo_cocoa_check_events` halting playback. [This Apple Doc](https://developer.apple.com/library/mac/#documentation/Cocoa/Conceptual/EventOverview/EventArchitecture/EventArchitecture.html) goes more in depth on the event model topic.
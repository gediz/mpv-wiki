TL;DR version only

* Dependencies that were installed using brew need to be installed using the option ``--build-bottle``, otherwise they may not run on other CPU generations.
* To make mpv compatible with older systems, both ffmpeg and mpv (and ideally all other dependencies) need to be compiled against the older SDK.

``CFLAGS=$CFLAGS"-mmacosx-version-min=10.8 -isysroot /Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX10.8.sdk"``

ffmpeg: ``./configure --extra-cflags="$CFLAGS" ...``

mpv: ``... CFLAGS="$CFLAGS" ./waf configure ...``


To bundle the dependency libs, run this in mpv's folder:
``TOOLS/osxbundle.py build/mpv``
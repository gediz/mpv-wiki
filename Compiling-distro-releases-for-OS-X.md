TL;DR version only

* Dependencies that were installed using brew need to be installed using the option ``--build-bottle``, otherwise they may not run on other CPU generations.
* To make mpv compatible with older systems, both ffmpeg and mpv (and ideally all other dependencies) need to be compiled with ``-mmacosx-version-min=10.8``:

ffmpeg: ``./configure --extra-cflags="-mmacosx-version-min=10.8" ...``

libass: ``CFLAGS="-mmacosx-version-min=10.8" ./configure ...``

mpv: ``CFLAGS="-mmacosx-version-min=10.8" ./waf configure ...``


To bundle the dependency libs, run this in mpv's folder:
``TOOLS/osxbundle.py build/mpv``

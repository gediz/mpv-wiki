If you are any of the people below, please contact us!
Send a mail to nfxjfg@googlemail.com, or post on: https://github.com/mpv-player/mpv/issues/2033


People whose email addresses are not valid anymore
------------------------------------
- Nick Kurshev <nickols_k@mail.ru> (user terminated) nickols_k@users.sourceforge.net (unknown user) (refactored old dec_audio.c code)
- adland <adland123@yahoo.com> (account gone) (url escaping fix, implicit contribution to ao_alsa, dvd:// command line parsing)
- Balazs Tibor <tibcu@sch.bme.hu> (user unknown) (small fixes: -frames 0, reset frame drop stats on new files)
- Alan Curry <pacman@world.std.com> (relatively trivial changes to vd_ffmpeg.c and demux_lavf.c and other areas, most contributions in removed code)
- Tom Lees <tal26@cam.ac.uk> (trivial ao_alsa patch, code was probably removed)


People who were contacted, but did not reply
------------------------------------------------
- Michel Lespinasse (part of his libmpeg2 video output changes might have been used as skeleton for vo.h - NOTE: probably doesn't matter, as we won't relicense the X11 code, and other than that literally nothing is left)
- Dénes Balatoni (introduces demux_control, also early slave commands for getting time/position, probably turned into later properties)
- kiriuja (audio track runtime switching be54f4813fdc9, option parser changes 43844d090c55, subtitle loading stuff (not sure if removed/replaced), video equalizer fix, some early slave mode things)
- Ville Syrjälä (svn name syrjala, did vo_dfbmga.c, which we removed, but a patch for nv12 touches other areas) (agreement probably not needed - everything removed)
- seru (OSD changes 8d190244d21a4d4, some other insignificant changes)
- Eviv Bulgroz (messes with stream seeking code in 2aa6acd9747ae, other changes not needed) (also apparently not a real name)
- Sam Dennis (probably not needed, his changes to demux_mkv.c were pretty much removed)
- R.L. Horn (small patch for ALSA audio output)
- Laurent (stream EOF fix a0f08fbebbdf)
- Chris Welton (small demux_lavf API change update 958c41d9b69843)
- Wei Jiang (small bug fixes in 2004, most memleaks)
- Paul Lebedev (track names in demux_mkv 62bfae140613321a, probably nothing copyrightable left)
- rguyom (some very early vd_ffmpeg.c fixes)
- "veal" in commit 116ca0c768219b10e, osd_show_property_text command, probably became show_text?
- Kir Kostuchenko (some TV changes - TV will stay GPL, but this touches common mplayer.c code that should become LGPL)
- Arwed von Merkatz (a patch for CDDA, the patches for removed fontconfig support are not needed)
- Bernd Ernesti (portability patches - unclear if anything survived, agreement probably not needed)
- Vladimir Kushnir (very early BSD portability changes, unclear if anything survived - probably not)
- James Warden (add 32 bit sample format to pulseaudio output, trivial)

- nVidia Corporation (most vdpau code, they said they're "looking into" the relicensing request)

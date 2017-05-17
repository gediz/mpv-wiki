This is a list of people who have agreed to relicense their MPlayer contributions to LGPL for the mpv project.  This might include some mplayer2-only and potentially mpv-only contributors too.

Note: Some agreements are partial or conditional, so this does generally not mean you can take their MPlayer code and change the license to LGPL.

mpv LGPL relicensing issue: https://github.com/mpv-player/mpv/issues/2033

mplayer-dev-eng thread: http://lists-archives.com/mplayer-dev-eng/39326-relicensing-mplayer-or-parts-of-it-to-lgpl.html

Have agreed and had a MPlayer svn/cvs username:
- adrian (Adrian Stutz)
- al
- al3x, alex
- albeu
- arpi
- astrange
- atlka
- atmos4/atmosfear
- attila
- ben
- bertrand
- bircoph
- cigaes
- cladisch
- colin
- compn
- corey
- diego
- eugeni
- eyck
- faust3
- filon
- folke
- gabrov
- gabucino
- gogothebee
- gpoirier
- henry
- hyc
- ib (except code under MPlayer's gui subdirectory)
- iive (but "LGPL 3.0 or later" only)
- ivo
- joey
- jonas
- kmkaplan
- komh
- kraymer
- ksorim
- laaz (probably with restrictions: excludes most of subreader.c from relicensing agreement)
- lgb
- lumag
- melanson
- mgraffam
- michael (under some conditions: http://lists.mplayerhq.hu/pipermail/mplayer-dev-eng/2016-September/073535.html)
- mosu
- mswitch
- nexus
- nicodvb (some core files - did not agree to relicense other parts, esp. encoding, dvb, dvd)
- nplourde
- ods15
- pl
- pontscho
- ptt, paultt
- ranma
- rathann
- rectalogic
- reimar
- reynaldo
- rfelker (only certain contributions: https://github.com/mpv-player/mpv/issues/2033#issuecomment-290464627)
- rsf
- rtogni, rtognimp
- siretart
- szabi, szabii
- tack
- uau
- ubitux
- ulion
- vayne (also contributed patches by mail as Erik Lunchpail, real name is different)
- voroshil
- wanderer (inverseparadox on github), with restrictions (see discussion on the github issue)
- zuxy
- zybi (Artur Zaprzala)

Partial map of svn usernames: https://ffmpeg.org/pipermail/ffmpeg-devel/2008-April/040487.html

Also have agreed (but no username, or have not contributed to MPlayer directly, or contributed to mplayer2/mpv):
- Markus Appel
- Erik Auerswald (only code in mpv, not any potential new code in MPlayer)
- Jens Axboe
- Michael Behrisch
- Fabrice Bellard
- Rocky Bernstein
- Arnaud Boulan
- Joachim Breitner
- Oswald Buddenhagen
- Angelo Cano
- Davide Capodaglio
- Mathieu Castets ("matthieu")
- Bryan Chan
- Hugo Chargois
- chocolateboy
- Evgeny Chukreev
- Dan Villiom Podlaski Christiansen (danchr)
- Kees Cook
- Steve Davies
- devik
- Daniel Dawson
- Romain Dolbeau
- Arne Driescher
- Aleksander V. Dyomin
- "eng"
- Johannes Feigl
- Andy Lo A Foe
- Paul-Francois Fontigny
- Peter Fordham
- Kilian A. Foth
- Fabian Franz
- German Gomez Garcia
- Lars Gemeinhardt
- Emanuele Giaquinta
- Steaphan Greene
- Pascal Haakmat
- Derk-Jan Hartman
- Sebastian Hegler
- Rik Hemsley
- Bryan Henderson
- hephooey (at gmail.com)
- Jens Hoffmann
- Loring Holden
- Aaron Holtzman (anything remaining in mpv)
- Stefan Hühner
- Panagiotis Issaris
- Robert Juliano
- Nicholas Kain
- Yuriy Kaminskiy
- Alexander Kanavin
- Wojtek Kaniewski
- Jürgen Keil
- Anton Khirnov
- Konstantin Khlebnikov 
- Martin Kebert (Kmarty)
- Gerd Knorr
- Emil Kohn (emild)
- Tomas Konir
- Ilya Konstantinov
- Kevin DeKorte
- Aaro Koskinen
- Onur Küçük
- Roland Kuhn
- Sang-Uok Kum
- Janusz Krzysztofik
- Krister Lagerstrom
- Dave Lambley
- Eric Lammerts
- Francesco Lavra
- Bruno Lecointre
- Matthias Lederhofer
- Timothy Lee
- Jerome Levreau (j.a.l)
- Oskar Liljeblad
- Hector Martin
- Sean McGovern
- Rob McMullen
- Federico Menarini
- Benson Mitchell
- Jack Moffitt
- Steve(n) Mueller
- Lauri Mylläri
- Alexander Neundorf
- Martin Oberzalek
- Magne Oestlyngen
- Christian Ohm
- Dan Oscarsson
- Attila Ötvös (oatilla)
- Trent Piepho
- Joakim Plate (elupus)
- Lennart Poettering
- Mikulas Patocka
- Zongyao Qu
- Shachar Raindel
- Markus Rechenberger
- Uwe Reder
- Thomas Reitmayr
- Robert Riches
- Gregor Riepl
- Chris Roccati
- Frank Scherthan
- Christian Schmidt
- Gordon Schmidt
- Mathieu Schroeter
- Steven M. Schultz
- Stanley Seibert
- Tristan Seligmann
- Jeremy Huddleston Sequoia
- Vlad Seryakov
- ShadowJK (on IRC)
- Stephen Sheldon
- Alex Sisson
- Jesper Svennevid
- Mike Swieton
- Gianluigi Tiesi
- Pedro Larroy Tovar
- Vladimir Umnov
- Giorgio Vazzana
- Dennis Vshivkov
- Nikolai Weibull
- Per Wigren
- Marcin Wojdyr
- Tim Wojtulewicz
- Timothy J. Wood
- Eric Yagerlener
- Zhou Zongyi

MPlayer developers who have replied, but have not given a final answer, and want to think about it:
- joyping (ao_alsa author, although relicensing it might fail due to other missing replies)

In progress:
- Gwenole Beauchesne (needs to go through corporate to get permission, or we will make vo_vaapi LGPL only, and replace the vaapi code involved with vo_opengl)
- nVidia (they said they will "look at it", low hopes, we'll probably just replace all vdpau code involved with vo_opengl)

Have disagreed with relicensing:
- anders (did the audio filter chain - will be replaced by libavfilter)
- Tristan z80@oceanfree.net (2 patches, all code most removed)
- Luca Abeni (basically `video/fmt-conversion.c`, code will be replaced)
- cehoyos (probably, all his code will be replaced, some tricky parts)

The list of people who have yet to reply is here: https://github.com/mpv-player/mpv/wiki/List-of-missing-MPlayer-LGPL-relicensing-agreements

A few of these agreements were received via the mplayer-dev-eng mailing list, a few on IRC, a moderate amount in the relicensing github issue, and most via personal mail.

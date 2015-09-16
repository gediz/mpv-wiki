Generally, using FFmpeg over Libav is recommended for mpv. The only reason is that FFmpeg has more features.

The main difference between these projects is in development methodology.

Libav:
- Tries to cleanup the API. Many (relatively) recent FFmpeg API improvements were actually just merged from Libav. Without Libav, there wouldn't be e.g. refcounted AVFrames and AVPackets.
- Tries to cleanup the code, which eventually will have security and performance benefits. Only hackable and understandable code can actually be improved.
- Tries to do things correctly. Lots of thought is put into selecting the technically best solution for a problem. Energy is spent to resist the temptation to just pile up stuff as it comes and goes.
- Strict code reviews. Libav prides itself on this, but it's a mixed bag. Some of it might contribute to development stagnation.
- Suffers from a lack of manpower, drive-by contributions, and 3rd party testing. FFmpeg is winning. Most of these points are due to lack of exposure; if more people use FFmpeg, more people will report bugs. _(All the users from having Libav be shipped instead of FFmpeg on both Ubuntu and Debian don't count for the sake of this poor attempt at self-victimisation.)_
- Pretends FFmpeg doesn't exist, though sometimes merges individual patches.
- Developers spend time making derogatory statements about FFmpeg on various websites and GitHub wikis as well as sending [legal threats devoid of substance](https://ffmpeg.org/threat1.png) and instead of developing software.
- Makes changes to the command line interface just to make scripts written for Libav incompatible with FFmpeg.
- Home to the same people who forced the mplayer/mplayer2 split, only this time their attempt at hijacking a project failed as Bellard stepped out from the shadows and let them know that claiming ownership of trademarks, infrastructure and maintainership over FFmpeg is not something that can be done with a mailing list posting.

FFmpeg:
- No effort is made to cleanup the API. The developers don't even understand why this would be necessary. The path of least resistance is preferred, so new features tend to build upon old API mistakes and making them worse. You hate the really big AVCodecContext struct with its dozens of fields? FFmpeg wants to add a new field every other month or so.
- In fact, there is resistance against cleaning up APIs to prevent breaking downstreams. Downstreams often complain about _both_ API breakages and the API being bad, but sometimes you can only improve the API by breaking it. But even long-deprecated and very bad APIs (like the old lavc resampler or deinterlacer) are retained.
- Nothing ever gets deleted. No matter how useless something is, it is retained, because it could be "useful for someone" (of course without pointing out who that someone is, because this someone rarely ever exist).
- Piles hacks upon hacks. A patch is questionable both in implementation and the improvement it adds? Doesn't matter, merge anyway. Someone wants to add a half-baken API half of the developers are against? It gets merged. Completely useless filters easily get in as well; apparently, as long as "it does what the documentation says", it can get in (even if it's useless). More features = better, fuck code quality. [Of course, "fuck code quality" is only bad when FFmpeg says it](http://codecs.multimedia.cx/?p=674).
- Weak code reviews. Reviewer's concerns are ignored, and often stuff is pushed without review or without even showing up on the mailing list.
- Pretends Libav doesn't exist, but merges absolutely everything it does. Sometimes with consequences; for example there are now 2 prores decoders, and 3 prores encoders.

Note: this is my personal opinion, and mostly an expression about my frustration with the FFmpeg development process. It isn't necessarily neutral or free of my own personal faults and misconceptions, but rather absolutely littered with it.
Generally, using FFmpeg over Libav is recommended for mpv. The only reason is that FFmpeg has more features.

The main difference between these projects is in development methodology.

Libav:
- Tries to cleanup the API. Many (relatively) recent FFmpeg API improvements were actually just merged from Libav. Without Libav, there wouldn't be e.g. refcounted AVFrames and AVPackets.
- Tries to cleanup the code, which eventually will have security and performance benefits. Only hackable and understandable code can actually be improved.
- Tries to do things correctly. Lots of thought is put into selecting the technically best solution for a problem. Energy is spent to resist the temptation to just pile up stuff as it comes and goes.
- Strict code reviews. Libav prides itself on this, but it's a mixed bag. Some of it might contribute to development stagnation.
- Suffers from a lack of manpower, drive-by contributions, and 3rd party testing. FFmpeg is winning. Most of these points are due to lack of exposure; if more people use FFmpeg, more people will report bugs.
- Pretends FFmpeg doesn't exist, though sometimes merges individual patches.

FFmpeg:
- No effort is made to cleanup the API. The developers don't even understand why this would be necessary. The path of least resistance is preferred, so new features tend to build upon old API mistakes and making them worse. You hate the really big AVCodecContext struct with its dozens of fields? FFmpeg wants to add a new field every other month or so.
- In fact, there is resistance against cleaning up APIs to prevent breaking downstreams. Downstreams often complain about _both_ API breakages and the API being bad, but sometimes you can only improve the API by breaking it. But even long-deprecated and very bad APIs (like the old lavc resampler or deinterlacer) are retained.
- Nothing ever gets deleted. No matter how useless something is, it is retained, because it could be "useful for someone" (of course without pointing out who that someone is, because this someone rarely ever exist).
- Piles hacks upon hacks. A patch is questionable both in implementation and the improvement it adds? Doesn't matter, merge anyway. Someone wants to add a half-baken API half of the developers are against? It gets merged. Completely useless filters easily get in as well; apparently, as long as "it does what the documentation says", it can get in (even if it's useless). More features = better, fuck code quality.
- Weak code reviews. Reviewer's concerns are ignored, and often stuff is pushed without review or without even showing up on the mailing list.
- Pretends Libav doesn't exist, but merges absolutely everything it does. Sometimes with consequences; for example there are now 2 prores decoders, and 3 prores encoders.

Note: this is my personal opinion, and mostly an expression about my frustration with the FFmpeg development process. It isn't necessarily neutral or free of my own personal faults and misconceptions.
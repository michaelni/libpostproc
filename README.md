libpostproc README
==================

libpostproc is a library for filtering images and videos.
It currently supports the MPEG4 deblocking and deringing filters and
some old basic deinterlacing methods and old basic denoise.
These deblocking methods are effective on a wide range of old
formats, including jpeg, mpeg1, mpeg2, mpeg4, h261, h262, h263,
msmpeg4v1, msmpeg4v2, msmpeg4v3 and many other similar formats.

libpostproc is supported by ffmpeg, mplayer and likely many other
media players.
This code was split out from FFmpeg and many bits and pieces from
FFmpeg remain.
In code that is shared with FFmpeg (like the build system)
the goal is to keep differences to a minimum, to allow easy future
updates.

That said, the Author is open minded and would certainly welcome
contributions which extend the scope of libpostproc beyond this.
For example an API supporting a wider range of pixel formats and
more complex filters. And also any general filterm, not just
postprocessing would be welcome.
Or in other words, if you want to turn libpostproc in a replacement
for gstreamer, your pull request could be accepted!
Also LGPL filters with a way to choose the license runtime would be
welcome.
Bascially, if you have a cool idea, AI, GPU accel, anything, it likely
is welcome!


## Documentation

The offline documentation is available in the **doc/** directory.

The online documentation is available in the main [website](https://ffmpeg.org)
and in the [wiki](https://trac.ffmpeg.org).

### Examples

Coding examples are available in the **doc/examples** directory.

## License

libpostproc codebase is GPL-licensed currently. If there is demand
relicensing to LGPL can be discussed but requires all authors to agree.

Please refer to the LICENSE file for detailed information.

## Contributing

Probably a pull request on github is easiest, but you can send the author
a mail with patch.

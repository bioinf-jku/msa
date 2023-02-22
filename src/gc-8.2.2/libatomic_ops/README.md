# The atomic_ops library (`libatomic_ops`)

IN NEW CODE, PLEASE USE C11 OR C++14 STANDARD ATOMICS INSTEAD OF THIS PACKAGE.

This is version 7.6.14 of libatomic_ops.


## Download

You might find a more recent/stable version on the
[Download](https://github.com/ivmai/libatomic_ops/wiki/Download) page, or
[BDWGC site](http://www.hboehm.info/gc/).

Also, the latest bug fixes and new features are available in the
[development repository](https://github.com/ivmai/libatomic_ops).


## Overview

This package provides semi-portable access to hardware-provided
atomic memory update operations on a number of architectures.  These might
allow you to write code:

* That does more interesting things in signal handlers.

* Makes more effective use of multiprocessors by allowing you to write
  clever lock-free code.  Note that such code is very difficult to get
  right, and will unavoidably be less portable than lock-based code.  It
  is also not always faster than lock-based code.  But it may occasionally
  be a large performance win.

* To experiment with new and much better thread programming paradigms, etc.

For details and licensing restrictions see the files in the "doc"
subdirectory.


## Installation and Usage

The configuration and build scripts for this package were generated by
Automake/Autoconf.  `./configure; make; sudo make install` in this
directory should work.  For a more customized build, see the output of
`./configure --help`.  To build it from the development repository,
`./autogen.sh` should be executed first.

Note that much of the content of this library is in the header files.
However, two small libraries are built and installed:

* `libatomic_ops.a` is a support library, which is not needed on some
  platforms. This is intended to be usable, under some mild restrictions,
  in free or proprietary code, as are all the header files.
  See doc/LICENSING.txt for more details about the licensing.

* `libatomic_ops_gpl.a` contains some higher level facilities.  This code is
  currently covered by the GPL.  The contents currently correspond to
  the headers `atomic_ops_stack.h` and `atomic_ops_malloc.h`.


## Platform Specific Notes

Win32/64: src/Makefile.msft contains a very simple Makefile for building
and running tests and building the gpl library.  The core `libatomic_ops`
implementation is entirely in header files.

HP-UX/PA-RISC: `aCC -Ae` won't work as a C compiler, since it doesn't support
inline assembly code.  Use cc.


## Feedback, Contribution, Questions and Notifications

Please address bug reports and new feature ideas to
[GitHub issues](https://github.com/ivmai/libatomic_ops/issues).  Before the
submission please check that it has not been done yet by someone else.

If you want to contribute, submit
a [pull request](https://github.com/ivmai/libatomic_ops/pulls) to GitHub.

If you need help, use
[Stack Overflow](https://stackoverflow.com/questions/tagged/atomic-ops).
Older questions on the site can be found by
[this query](https://stackoverflow.com/search?q=atomic_ops).
Older technical discussions are also available in `bdwgc` mailing list
archive - it can be downloaded as a
[compressed file](https://github.com/ivmai/bdwgc/files/1038163/bdwgc-mailing-list-archive-2017_04.tar.gz)
or browsed at [Narkive](http://bdwgc.opendylan.narkive.com) (please search
for _atomic_ keyword).

To get new release announcements, subscribe to
[RSS feed](https://github.com/ivmai/libatomic_ops/releases.atom).
(To receive the notifications by email, a 3rd-party free service like
[IFTTT RSS Feed](https://ifttt.com/feed) can be setup.)
To be notified on all issues, please
[watch](https://github.com/ivmai/libatomic_ops/watchers) the project on
GitHub.


## Copyright & Warranty

 * Copyright (c) 1991-1994 by Xerox Corporation.  All rights reserved.
 * Copyright (c) 1996-1999 by Silicon Graphics.  All rights reserved.
 * Copyright (c) 1999-2011 Hewlett-Packard Development Company, L.P.
 * Copyright (c) 2008-2021 Ivan Maidanski

The file armcc/arm_v6.h is also

 * Copyright (c) 2007 by NEC LE-IT.  All rights reserved.

The file gcc/avr32.h is

 * Copyright (c) 2009 Bradley Smith <brad@brad-smith.co.uk>

The file gcc/mips.h is

 * Copyright (c) 2005, 2007 Thiemo Seufer <ths@networkno.de>

The file gcc/sh.h is

 * Copyright (c) 2009 by Takashi YOSHII. All rights reserved.

Please be aware of the dual nature of the license of libatomic_ops,
see [LICENSING.txt](doc/LICENSING.txt) for the details.
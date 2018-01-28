Makeheaders
===========

This is a mirror-repo of the famous makeheaders tool with various fixes
and tweaks I made. The official upstream version is the "proper"
version to use, and can be found
[at their website](http://www.hwaci.com/sw/mkhdr/). If confused by why
this version is interesting, just use the upstream tool and ignore this
one. If you browsed this repo's changes and like/need them, then you
know what you are doing and I don't have to explain :-)

My main purpose for uploading this repo is to email the link to the
upstream authors so they can integrate some or all of the changes if they
want, which will hopefully make this mirror obsolete. If they accept all
the changes I will make a clear note of it here.

`makeheaders` is under a Simplified BSD License. See the comments near
the top of the file for copyright information.

I started making these changes because I came across an error, and
despite the various fixes I made I ran out of time to diagnose that
original error, and as it is not a showstopper for me anyway I am just
leaving it in the FIXME at the bottom of this README.

Any bug-reports of *the local changes I have made* can be
[reported to me](mailto:rowan@rowanthorpe.com) but anything to do with
the upstream tool itself should still be reported there.

Build instructions
------------------

A [CMake](https://cmake.org) file has been contributed, so if you are in a hurry (or lazy, not
confident compiling, or whatever), if CMake is installed you can do the following to build a
standard non-optimized executable and install it to your system's default custom-compilation
bin-dir (of course CMake must be installed):

```sh
mkdir build
cd build
cmake ..
make
sudo make install
```

`makeheaders` is plain ansi c, and doesn't depend on anything outside the standard library, so
should be buildable with any command along the lines of:

```sh
${COMPILER} ${WARNINGS_FLAGS} ${OPTIMIZATION_FLAGS} -o makeheaders makeheaders.c
```

Read the comments near the top of `makeheaders.c` to see how I build it with `gcc` in
mem-testing mode, stack-checking mode, and final mode, and for `valgrind` commandlines for
testing the resulting executable.

License
-------

Makeheaders is under the "2-Clause License" ("FreeBSD License"). See the license-header at the
top of the `makeheaders.c` file for details.

FIXME
-----

* CompleteForwardDeclarations does `abort()` when running `./makeheaders -local makeheaders.c`
  (seems to be an issue on static functions with no preceding declaration)

Authors
-------

Upstream author:
 [D. Richard Hipp](http://www.hwaci.com/drh/index.html)

Maintainer of this repo:
 [Rowan Thorpe](https://github.com/rowanthorpe)

Contributions:
 [xoviat](https://github.com/xoviat) - CMake file

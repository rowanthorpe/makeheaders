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
leaving it in the below FIXME.

Any bug-reports of *the local changes I have made* can be
[reported to me](mailto:rowan@rowanthorpe.com) but anything to do with
the upstream tool itself should still be reported there.

FIXME
-----

* CompleteForwardDeclarations does `abort()` when running `./makeheaders -local makeheaders.c`
  (seems to be an issue on static functions with no preceding declaration)

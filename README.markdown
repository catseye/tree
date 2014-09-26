`tree`
======

This is `tree`, a command-line tool that displays an indented directory tree,
similar to "The Tree Command for Linux" except simpler.  It:

*   is written in Python (tested with 2.7.6)
*   is small and has no dependencies besides Python
*   is in the public domain (see `UNLICENSE`)
*   is really quite crude
*   displays a summary of the directory structure by default (because to
    me, that's the point of this sort of tool: give me a conceptual overview of
    the directory structure at this point in the filesystem, so I can orient
    myself)
*   never follows symbolic links
*   supports one option, `--full`, which lists all files in each directory
    instead of giving you the summary
*   always outputs a `/` after each directory name
*   doesn't have any ASCII art (yet; it might someday as the lines do make
    it a bit easier to "read" the tree)
*   has no build/install system; either copy it to somewhere on your
    search path, or alter your search path to include the `script` directory
    in this repo, or use some system that solves this problem, like
    [toolshelf](http://catseye.tc/node/toolshelf).

Usage
-----

    tree [-f|--full] [DIRECTORY]

If DIRECTORY is not supplied, the current directory is assumed.

Related work
------------

*   [The Tree Command for Linux](http://mama.indstate.edu/users/ice/tree/) —
    GPL'ed and feature-bloated and has no automated build system (you're
    supposed to edit the Makefile by hand.)
*   [pyr/tree](https://github.com/pyr/tree) — fine if you're running OpenBSD
    I suppose, but I gave up on trying to port it to NetBSD and Linux and
    wrote this instead.

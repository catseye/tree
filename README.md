`tree`
======

_Version 1.2_

This is Cat's Eye Technologies' `tree`, a command-line tool that displays an
indented directory tree, similar to "The Tree Command for Linux" except simpler.
It:

*   is written in Python (Python 3 by default; also tested with 2.7)
*   is small and has no dependencies besides Python
*   is in the public domain (see `UNLICENSE`)
*   is really quite crude
*   displays a summary of the directory structure by default (because to
    me, that's the point of this sort of tool: give me a conceptual overview of
    the directory structure at this point in the filesystem, so I can orient
    myself)
*   never follows symbolic links
*   always outputs a `/` after each directory name
*   doesn't have any ASCII art (yet; it might someday as the lines do make
    it a bit easier to "read" the tree)
*   has no build/install system; either copy it to somewhere on your
    search path, or alter your search path to include the `script` directory
    in this repo, or use some system that solves this problem, like
    [shelf](http://catseye.tc/node/shelf).

Usage
-----

    tree [-f|--full] [-a|--all-files] [-1|--1-line] [-c|--count]
         [-w|--max-width <int>] [-x|--exclude <list>] [DIRECTORY]

If DIRECTORY is not supplied, the current directory is assumed.

The `--full` option lists each file in a directory on its own line.

The `--all-files` option includes files whose names begin with a
`.` character, which would otherwise be hidden.

The `--1-line` option lists a summary of the files in each directory
on one line, truncating the line if it is longer than the max-width.

The `--count` option causes a count of files in each directory to
be display instead of listing the files themselves.

If none of those options are given, all files in a directory are
listed compactly over multiple lines, in a "block".

The `--max-width` option can be used to set the length of truncation
or block-wrapping.  It defaults to the width of the terminal window
as returned by `stty size`, if that program can be run, otherwise 75.

The `--exclude` option sets the list of directory names to not descend
into (a comma-separated list).  It defaults to `venv`, `node_modules`,
`__pycache__`, and `.git`.

Related work
------------

*   [The Tree Command for Linux](http://mama.indstate.edu/users/ice/tree/) —
    GPL'ed and feature-bloated and has no automated build system (you're
    supposed to edit the Makefile by hand.)
*   [pyr/tree](https://github.com/pyr/tree) — fine if you're running OpenBSD
    I suppose, but I gave up on trying to port it to NetBSD and Linux and
    wrote this instead.

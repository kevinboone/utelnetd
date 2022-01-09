# utelnetd

Version 0.1.9

## What is this?

`utelnetd` is a very small telnet daemon, originally written by
Robert Schwebel and others. So far as I know, it hasn't been updated
by any of its original authors since 2003. I've modified it
(only small modifications were needed) to make it build cleanly,
and run properly, on modern Linux systems.
I've tested `utelnetd` mostly on Ubuntu 20.04.

## Why?

`utelnetd` remains useful in embedded systems, and in a small class of
highly-specialized applications that still need an unencrypted (and possibly
unauthenticated) text-mode network connection to a Unix system.
It's getting increasingly difficult to find the original source, and
I wanted to prevent it disappearing entirely.

The original code, and thus this version, was released under the terms of the
GNU Public Licence, v2.0.

## Notes

`utelnetd` does not need to be run as `root` although, of course, the
program specified as the login program (using `-l`) must be capable of
running as an unprivileged user. This, of course, rules out regular
login operations, but it's still possible to use telnet to run
specific utilities. Of course, software of this sort, that has its
origins in days when the Internet was less hostile, ought to be run
as an unprivileged user if possible. In fact, telnet should be avoided
completely, in any application where security is important.

Unlike the mainstream `in.utelnetd`, `utelnetd` does not need to be
run by `inetd` (or its modern equivalents). It's possible to start
`utelnetd` as an ordinary daemon process. It's even possible to run
multiple daemons on different ports, with different 'login'
programs if necessary.

I've added a command-line switch `-n` that disables printing of the
`/etc/issue` file when a new session is started.



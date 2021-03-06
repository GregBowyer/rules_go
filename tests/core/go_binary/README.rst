Basic go_binary functionality
=============================

.. _go_binary: /go/core.rst#_go_binary

Tests to ensure the basic features of go_binary are working as expected.

hello
-----

Hello is a basic "hello world" program that doesn't do anything interesting.
Useful as a primitive smoke test -- if this doesn't build, nothing will.

out_test
--------

Test that a `go_binary`_ rule can write its executable file with a custom name
in the package directory (not the mode directory).

goos_pure_bin
-------------

Tests that specifying the `goos` attribute on a `go_binary`_ target to be
different than the host os forces the pure mode to be on. This is achieved
by including a broken cgo file in the sources for the build.

many_deps
---------

Test that a `go_binary`_ with many imports with long names can be linked. This
makes sure we don't exceed command-line length limits with -I and -L flags.
Verifies #1637.

stamp_test
----------
Test that the `go_binary`_ ``x_defs`` attribute works correctly, both in a
binary and in an embedded library. Tests regular stamps and stamps that
depend on values from the workspace status script. Verifies #2000.

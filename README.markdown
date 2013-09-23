Testrig
====

Testing of interactive programs with file(s) containing setup commands
----------------------------------------------------------------------
This is useful when you are testing structures that require initialisation:
 * BSTs
 * Hash Tables
 * Flexarrays

You need to test various functions, but typing in some test data to initialise
the structure takes too long.


A first go
----------
Want to read in from a file, pipe that to a program, then take user input and
pipe that in, too.

    (cat testfile & cat) | stdbuf ./program

A couple of cats bound to the same pipe, and stdbuf stripping away buffering,
seems to work initially.

Next level
----------
Why not save your command history each time?

    (cat testfile & (cat | tee -a testfile)) | stdbuf ./program

Save your command history for the next session.

This repository is a collection of relaxed-memory litmus tests,
principally for the AAarch64, IBM POWER, and RISC-V architectures, and
with a few tests for MIPS and x86.  They are made available under a
BSD licence, in LICENCE, with AUTHORS as specified in the
subdirectories.

Each test is a .litmus file, in the format used by the
[http://diy.inria.fr/](diy) and
[http://www.cl.cam.ac.uk/users/pes20/rmem](rmem) tools:

- litmus7, for running tests experimentally on hardware
- diy7, for generating tests
- herd7, for running tests w.r.t. a herd axiomatic model
- rmem, for running tests w.r.t. various operational models

The tests are organised in directories first by architecture, then by
whether they involve mixed-size accesses or not, and then in some way
depending on how they were produced. Many of the tests were generated
by diy, and for those, where possible, we include the X.conf and/or
build.sh files used for the generation.  Other tests were hand-written
or adapted from some generated test.  The @ files collect useful
groups of tests.

Each test specifies an initial memory and multicore register state,
assembly code for each thread of the test, and a constraint on the
final state that typically identifies the execution of interest for
that test.  That execution might be observable or not on a particular
hardware implementation, and allowed or not in a particular model;
whether tests are observable or allowed is intentionally not specified
in the test files themselves.

Most test names are generated by diy. Some tests (a relatively small
fraction of the whole) appear in multiple subdirectories, where they
were generated as overlapping families.

The Makefile and mkindex.sh build a simple html index of the directory
structure, showing the number of tests.



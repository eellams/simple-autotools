### A simple automake project, compete with tests.

# Simple Autotools

A simple setup to use autotools to automate the build process. Currently this compiles a C program, however C++ is also supported (see `configure.ac` for more details).

For this example, a dynamic library, *libsomething*, is compiled from items in the src directory. See `src/Makefile.am` for further details.

The tests then link to *libsomething* to test functionality. See `tests/Makefile.am`.

Note that automake supports building libraries, executables etc. This can be achieved by editing the Makefile.am files, but I will leave this up to you :)

## Required packages
(Assuming you are running on a Debian-based system)

`sudo apt install automake check libtool`

## Setup:
Autotools needs to be initialised before building anything. This process reads the configure.ac file, and the Makefile.am files and produces the required Makefiles/scripts etc. for the build to run.

    $ cd <simple-autotools root directory>
    $ automake -i

## Build

    $ ./configure 
    $ make build
    
Binaries will be placed in the src directory.

## Tests
Tests are defined in `tests/Makefile.am`. If the return code of the test executable is 0, then the test passes. If the return code is non-zero, then the test fails.
You as the user need to decide what conditions each test is running, and what the pass/fail conditions are.

Personally, I find tests useful for development as you can focus on a single feature in each test. Once all individual functionality has been implemented, one can write

    $ make check`

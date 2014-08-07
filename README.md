Higgs
=====

[![Build Status](https://travis-ci.org/maximecb/Higgs.png?branch=master)](https://travis-ci.org/maximecb/Higgs)

A JIT compiler for JavaScript targetting x86-64 platforms.

**Requirements:**

- D compiler ([DMD](http://dlang.org/dmd-linux.html) recommended)
- POSIX compliant OS (Linux, Unix, MacOS X)
- Python 2.7 (if regenerating object layouts)
- x86 64-bit CPU
- GNU make

**Quickstart:**

*Get the source:*
 
`git clone https://github.com/maximecb/Higgs.git && cd Higgs/source`

*Compile a binary:*

NOTE: if you run a non-Linux OS like FreeBSD you may not have `GNU make` installed. You may need to install the "gmake" package or otherwise aquire `GNU make`.

 
`make all`
generates a binary `higgs` in the source directory.

*Compile a release binary:*

`make release`
generates a binary `higgs` in the source directoy.

*Install (optional):*
 
`make install`
generates a release binary using the `release` target, then copies the `higgs` binary to `/usr/bin` and the runtime files to `/etc/higgs`. The installation directories for
the binary and runtime files may be changed with `BIN_DIR` and `LIB_DIR` respectively:
```sh
make install BIN_DIR=/my/bin/dir LIB_DIR=/my/lib/dir
```


NOTE: you may need to run `make install` with `sudo`.

*Cleanup:*
 
`make clean`
will remove any binaries in the source directory.

*You may wish to run the unit tests:*

`make test`
generates a binary `test-higgs` and tests its proper functioning.

For further info, see the `makefile`.

**Usage:**

`higgs` will start Higgs and give you a REPL (read-eval-print loop).

To execute one or more files, pass them to `higgs`:

`higgs file1.js file2.js`

The `--e` option accepts a string to execute:

`higgs --e "var x = 4; x = x + 5; print(x)"`

The `--repl` option will start a REPL after evaluating a string and/or files:

`higgs --repl file1.js` will evaluate `file1.js` and then start a REPL.

`higgs file1.js` will evaluate `file1.js` and then exit.

The `--jit_dumpasm` option will dump the assembler code generated by the JIT to the console.

Command-line arguments can be passed to a JS script using the `--` separator, as follows:

`higgs file1.js file2.js -- 0 1 2`

These arguments will be evaluated as JS code in the global scope and the resulting values inserted in a global `arguments` array.

**Notes:**
 - You may wish to use `rlwrap` for a better REPL experience.

More
=====

Documentation for Higgs and included libraries can be found in the [Higgs Wiki](https://github.com/maximecb/Higgs/wiki).

You can follow the development of Higgs on [Maxime's blog](http://pointersgonewild.wordpress.com/category/higgs/).

Come chat with us in [\#higgsjs](http://webchat.freenode.net/?channels=higgsjs) on [Freenode](http://freenode.net/).

Follow Higgs news and discussion by subscribing to [r/higgsjs](http://www.reddit.com/r/higgsjs/) on reddit.

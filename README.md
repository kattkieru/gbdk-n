# gbdk3_stdlib

This is a fork of https://github.com/andreasjhkarlsson/gbdk-n. Andreas got a good chunk of the old, useful GBDK libraries working in sdcc and I'm using theirw work as a starting point for my own toolchain.

Building requires that you _not_ link against sdcc's standard crt0. Currently, the crt0.s file in this repo seems to lock the cart type, so you may need to add a copy to your file if you need a larger cart.  I'll investigate as I go.



#### Background

The Gameboy Development Kit (GBDK) is an SDK for developing applications/games for the gameboy platform. The library bundles a custom version of the Small Device C Compiler (SDCC), libraries & examples.

The latest update of GBDK was a long time ago (mid 2002). Since then the SDCC compiler has gotten native support for compiling and linking fully functional gameboy roms. 

However GBDK is still useful since it contains libraries for developing applications for the gameboy family. This project aims to update the libraries to be compatible with new versions of SDCC and provide helpers for building roms.

The GBDK libraries were copied from the latest source release on sourceforge: http://sourceforge.net/projects/gbdk/files/gbdk/2.96/

#### Usage

##### Building the library:
`$ make`

##### Building the examples:
`$ make examples`

##### Building custom ROMs:
NOTE: All commands listed below are simply wrappers to SDCC, see the SDCC documentation for flags and general usage.

* Compile / assemble .c files and .asm files into .rel files using the gbdk-n-compile.sh and gbdk-n-assemble.sh commands respectively.
* Link together one or more .rel files into an .ihx file using the gbdk-n-link.sh command.
* Create a ready to use .gb rom file from the .ihx file with the gbdk-n-make-rom.sh command.

For exact commands, please see the Makefiles for the example programs.

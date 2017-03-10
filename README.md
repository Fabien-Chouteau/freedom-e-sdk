# README #

This repository, a clone of the SDK maintained by SiFive, Inc, makes it easy to
get started developing Ada software for the Freedom E RISC-V platform.

In addition to the standard SDK, this repository will compile the GNAT Ada
compiler and also use the Ada_Drivers_Library project to control the HiFive1
board.


### Setting up the SDK for Ada ###

First, clone this repository:

```
git clone --recursive https://github.com/sifive/freedom-e-sdk.git
```

Ubuntu packages needed:

	$ sudo apt-get install autoconf automake libmpc-dev libmpfr-dev libgmp-dev gawk bison flex texinfo libtool libusb-1.0-0-dev make g++ pkg-config libexpat1-dev zlib1g-dev gnat

Next, build the tools:

```
cd freedom-e-sdk
make tools
```

If your machine has enough resources, you can speed up the build process by adding `-j n` to `make`, where `n` is the number of processors of your build system.

To compile a bare-metal RISC-V Ada program:

```
cd freedom-e-sdk
make ada_blinky_build
```

You can ignore the "libraries are not supported on this platform" warning. It
just means that gprbuild doesn't know this platform yet.


To install the Ada program on the board:

```
sudo make ada_blinky_upload
```

To modify the Ada program:

```
gps -P Ada_Drivers_Library/examples/HiFive1/hifive1_example.gpr
```

you can then compile from the IDE and install the program on the board with the
command above.

### For More Information ###

Documentation, Forums, and much more available at

[dev.sifive.com](https://dev.sifive.com)

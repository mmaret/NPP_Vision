# Image Detail Filter

## Overview

This project aim to reduce details on a image. 
It could be used for:
* people with poor vision that will only be sensible to high contrast.
* cleaning dust after an image scan
* ...

Before:

![Before](data/morpion.png)

After:

![After](data/morpion_filtered.png)

## Code Organization

```bin/```
This folder hold compilation artifacts

```data/```
Set of sample images

```lib/```
Contains Cuda-sample library code as a git submodule

```src/```
The source code

```Makefile```
Build System

## Key Concepts

It perform a serie of erode and dilate on the image and its invert to remove the "small" dots

## Supported OSes

Linux

## Supported CPU Architecture

x86_64

## CUDA APIs involved

## Dependencies needed to build/run
[FreeImage](../../README.md#freeimage), [NPP](../../README.md#npp)

## Prerequisites

Download and install the [CUDA Toolkit 11.4](https://developer.nvidia.com/cuda-downloads) for your corresponding platform.
Make sure the dependencies mentioned in [Dependencies]() section above are installed.

Retrieve git submoules:

```
git submodule update --init 
```

## Build and Run

### Linux
The Linux bin is built using makefiles. To use the makefiles, change the current directory to the sample directory you wish to build, and run make:
```
$ cd <sample_dir>
$ make
```

## Running the Program
After building the project, you can run the program using the following command:

```bash
make run
```

This command will execute the compiled binary, filter the input image (Lena.png), and save the result as Lena_filtered.pgm in the data/ directory.

If you wish to run the binary directly with custom input/output files, you can use:

```bash
./bin/imageDetailFilterNPP --input data/Lena.png --output data/out.png
```

- Cleaning Up
To clean up the compiled binaries and other generated files, run:


```bash
make clean
```

This will remove all files in the bin/ directory.

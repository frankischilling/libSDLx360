# libSDLx360

libSDLx360 is an Xbox 360 implementation of the Simple DirectMedia Layer (SDL) library.  
This repository is a GitHub mirror and archival copy of the original libSDLx360 source code.

The code provides a custom SDL 1.2 style implementation for homebrew on modified Xbox 360 consoles.  
It replaces the original Xbox DirectX 8 based rendering and audio paths with Direct3D 9 and XAudio2 for the Xbox 360 platform.

Only source code is included in this repository. No compiled binaries or XEX files are provided.

---

## Overview

Simple DirectMedia Layer (SDL) is a cross platform multimedia library that provides low level access to:

- Audio  
- Keyboard  
- Mouse  
- Joystick  
- 3D hardware via OpenGL  
- 2D video framebuffer  

It is used by media players, emulators, and many games.

libSDLx360 is a port of SDL for the Xbox 360. It is based on an earlier libSDLx library written for the original Xbox, updated to run on Xbox 360 hardware using:

- Direct3D 9 for video  
- XAudio2 for audio  
- Xbox 360 controller input  
- Xbox 360 specific filesystem and threading support  

---

## Repository Contents

The archive contains three main components:

- `libSDLx360`  
  Main SDL port for Xbox 360. This contains the core library source code.

- `SDL_ttf360`  
  SDL_ttf port for Xbox 360, providing TrueType font rendering support.

- `SDLTest`  
  A sample project that demonstrates a simple SDL based test application running on the Xbox 360.

---

## Features

The following functionality is implemented and known to work in the included versions:

- Video using Direct3D 9  
- Audio output using XAudio2  
- Threads and basic synchronization  
- Filesystem access appropriate for Xbox 360 homebrew  
- Joystick support for Xbox 360 controllers (players 1 to 4)  
- SDL_ttf based font rendering (via `SDL_ttf360`)  
- Example SDL test application (`SDLTest`)  

Basic SDL subsystems are up and running. Graphics, audio, threads, filesystem, and joysticks are all implemented and functioning.

---

## Version History

### V0.02 (2011-02-09)

The V0.02 version of libSDLx360 contains several important fixes and improvements:

- Keyboard handling fixes  
  - Correct handling of Shift, Alt, and Control keys  
  - Resolves keyboard issues in applications such as XeDosBox  

- Joystick bug fix  
  - Corrected behavior where controllers 2 to 4 were polling against player 1  
  - Resolves controller mapping issues in titles such as Super Mario Wars  

- Mouse emulation  
  - Left analog stick mapped to mouse movement  
  - Button A mapped to left mouse button  
  - Button B mapped to right mouse button  

- Video adjustments  
  - Vertex buffer adjusted so rendering fits inside the television safe area  

### V0.01

The original V0.01 release introduced the initial Xbox 360 port, including:

- Port of the original Xbox libSDLx library to Xbox 360  
- Replacement of DirectX 8 based audio and video calls with Direct3D 9 and XAudio2 equivalents  
- Core SDL subsystems brought up on Xbox 360:  
  - Graphics  
  - Audio  
  - Threads  
  - Filesystem  
  - Joysticks  

Only source code to build the libraries was provided. No binaries were included.

---

## Building

To build libSDLx360 and the associated libraries, you will need:

- Official Xbox 360 XDK (Xbox Development Kit)  
- Supported Microsoft Visual Studio version that integrates with the XDK  
- Standard C and C++ toolchain configured for Xbox 360 development  

General steps:

1. Open the provided project or solution files from the XDK compatible version of Visual Studio.  
2. Configure include paths and library paths as required by your XDK installation.  
3. Build the static or import libraries for libSDLx360 and SDL_ttf360.  
4. Link the resulting libraries into your Xbox 360 homebrew application.  
5. Use the `SDLTest` project as a reference for configuration and usage.

This repository does not include any XDK files, libraries, or headers. You must provide those from your own licensed XDK installation.

---

## Usage

Once built, libSDLx360 can be used much like a standard SDL 1.2 environment, with the usual initialization and main loop patterns, for example:

- Initialize SDL subsystems  
- Create a window or video surface  
- Set up audio and input handling  
- Enter a main loop for rendering and event processing  

The `SDLTest` project demonstrates a simple SDL test application running on the Xbox 360. It is a good starting point for understanding:

- How to initialize SDL on Xbox 360  
- How to handle controller input  
- How to render basic graphics  

---

## Known Limitations and TODO (Historical)

According to the original notes, the following items were planned or incomplete:

- Additional performance optimizations  
- Mouse, keyboard, and CD-ROM handling were initially incomplete or only partially implemented  
- SDL_mixer had not yet been ported  

Some of these gaps were partially addressed in V0.02 (for example, mouse emulation and improved keyboard support), but the library should still be considered experimental and primarily suited for homebrew and hobby projects.

---

## Contributing

This repository is intended as a historical archive and mirror of the original libSDLx360 work. Contributions are welcome in the form of:

- Fixes and cleanups  
- Documentation improvements  
- Build instructions for specific XDK versions  
- Non intrusive enhancements that preserve the original structure and intent

If you have additional patches, missing files, or older versions of the code, please consider opening an issue or pull request so they can be preserved here.

---

## Legal Notes

- This repository contains source code only. No compiled binaries or XEX files are included.  
- You must have a valid license for the Xbox 360 XDK to build and run this code on Xbox 360 hardware.  
- All original rights remain with the original author(s) of libSDLx360 and with the SDL project for any SDL derived components.  

This mirror is provided for archival, educational, and homebrew development purposes.

---

## Credits

The original libSDLx360 implementation and the underlying libSDLx work for the original Xbox were created by members of the Xbox homebrew community. Their work enabled SDL based applications, emulators, and games to run on Xbox consoles.

Greets to the scene.

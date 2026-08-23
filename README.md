# This PsyCross fork has been altered to make it more compatible with Silent Hill. In essence, it may also be more compatible with other games, but that hasn't been tested. Documentation for the changes will be added at some point.

# Psy-Cross (Psy-X)
![](https://i.ibb.co/PFNnw4G/PsyCross.jpg)

Compatibility framework for building and running Psy-Q SDK-based PlayStation games across other platforms.

### Implementation details
- High-level *PlayStation API* reimplementation that translates its calls into modern/compatible APIs
- Psy-Q-compatible headers
- Implements the Geometry Transformation Engine (GTE) in software and adapts its macros and calls
- Optimized Precise GTE Vertex Cache with *modern 3D hardware perspective transform* and *Z-buffer* support (PGXP-Z)
- *LibSPU* with ADPCM decoding on OpenAL (SPU-AL)
- *LibGPU* with PlayStation-style polygon and image handling
- *LibCD* with ISO 9660 BIN/CUE image support through the PlayStation CD API
- Already proven to be *95% compatible* with the Psy-Q PlayStation SDK; Psy-X games look almost identical to the PlayStation games
- You can bring your game to the *Web with Emscripten* support

### Folder structure
- `src/gpu`: PSX GPU linked lists and polygon handling routines
- `src/gte`: PSX GTE and PGXP-Z implementation
- `src/render`: OpenGL renderer and PSX VRAM emulation
- `src/pad`: Controller handling
- `src/psx`: Implementations of Psy-Q-compatible libraries (**libgte, libgpu, libspu, libcd ...**)
- `include/psx`: Headers for Psy-Q-compatible libraries (**libgte, libgpu, libspu, libcd ...**)
- `include/PsyX`: PsyCross interfaces (**window management, configuration, renderer, PGXP-Z**)

### Dependencies
- OpenAL Soft (1.21.x or newer)
- SDL2 (2.0.16 or newer)

## TODO
- CMake dependency/build scripts
- Add some missing **LibGTE** functions
- MDEC implementation in **LibPress**
- CD Audio/XA decoding and playback
- SPU Attack-Decay-Sustain-Release (ADSR) support, *maybe through its own mixer?*

### Credits
- SoapyMan - more GTE functions, SPU-AL, PGXP-Z
- Gh0stBlade - original source/base [(link)](https://github.com/TOMB5/TOMB5/tree/master/EMULATOR)

---
layout: post
tags: 
- n64
title: N64 RSP - Reality Signal Processor
image:  /public/N64/N64RealitySignalProcessor.jpg
thumbnail: /public/consoles/Nintendo 64.png
videocarousel:
  - title: Video 1
    image: http://img.youtube.com/vi/nqqTfERxUvA/0.jpg
    youtube: 'nqqTfERxUvA'
permalink: /n64rsp
breadcrumbs:
  - name: Home
    url: /
  - name: N64
    url: /n64
  - name: N64 RSP - Reality Signal Processor
    url: #
recommend: n64
editlink: /n64/N64RSP.md
---

The N64 Reality Signal Processor (RSP) is the part of the Reality Co-Processor (RCP) that deals with data transform. It is a MIPS-based cpu like the main R4000 cpu but it also contains additional 8-bit vector opcodes[^1].

The data transform is crucial for both graphics and audio data and so microcode is used to implement graphics and audio routines that run on the RSP.

# RSP for Graphics
Common tasks given to the RSP for graphical data processing are:
* Lighting calculations
* Display List decoding
* Shading
* Level of Detail culling (LOD)
* Clipping
* Vertice Transforms (translate, scale, rotate)

# RSP for Audio
Common tasks given to the RSP for graphical data processing are:
* Wavetable Audio format decoding
* Midi Audio processing
* MP3 decoding (Conkers Bad Fur Day)

# Microcode
Although you can initially think of the RSP microcode as similar to a modern Shader language, as they are both used to implement a programmable graphics pipeline. 
It wasn’t common for developers to write their own microcode for their games until near the end of the N64 lifecycle. 

So most early games used pre-written microcode developed by SGI and Nintendo and used it like a fixed function graphical pipeline.

The main reason for the lack of custom microcode development by 3rd party games is due to the poor tools and documentation provided by nintendo. Not to mention the complexity of programming for it and no debugger was provided [^1].

The main output of the RSP microcode tends to be either graphical rasterization commands for the RDP or audio buffers for the DAC.

# Known Microcodes
The list of RSP Microcodes provided by the Official Nintendo64 SDK are as follows:
* gspFast3D - most full features, includes shading fog etc
* gspF3DNoN - same as Fast3D but without near-clipping
* gspLine2D - does not render triangles so it gives a wireframe effect 
* gspSprite2D - efficient for 2D sprite images
* gspTurbo3D - faster than `Fast3D` but reduced precision.

## Variations of Fast3D  (F3D)
Fast3D is a very common microcode provided with the N64 SDK, it went through multiple iterations during the N64 lifecycle.

It started with the standard `Fast3D` used in the game Super Mario 64.

It then evolved into the Extended version known as `Fast3DEX` used in Mario Kart 64.
Multiple versions were released of this microcode including `Fast3DEX2` the second major version released and promised accelerated RSP processing speeds [^7]. 

Later other modifications of Fast3D emerged such as `F3dZEX` which stands for Fast 3D Zelda Extended used in Zelda 64 [^6].

### F3DLX - No Texture compression
F3DLX (Fast3DLimitedteXture) was an optimized version of the original Fast3D by removing texture compression support, this was deprecated after version 1 and was not carried over to F3DEX2 [^7].

### F3DLP - sub-pixel calculations ommited
F3DLP (Fast3DLimitedPixel) was an optimized version of the original Fast3D by removing subpixel calculation support, this was deprecated after version 1 and was not carried over to F3DEX2 [^7].

### .REJ (e.g F3DLX.Rej)
The microcode files that have .Rej in the name subsitute the clipping process for the lighter `reject processing` feature.

For example this is more efficient for rendering characters as clipping is not required but would not be suitable for landscapes where clipping is required [^8].

### .NoN (e.g gspF3DEX.NoN.fifo.o)
The microcode files that have .NoN in the name remove the `Near Clip` feature, which can be more efficient if you make sure to render your objects in the order from furthest away to closest as no clipping will take place [^8].

Presumably NoN stands for `No Near-Clip` but this is unconfirmed.


## Sending RSP result to RDP (.fifo, .dram etc)
The result of the RSP graphical calculations need to be sent to the Reality Display Processor or RDP in order to rasterize the pixels for the game. There are multiple different ways to copy the result from RSP to RDP and each provide a slightly modified version of the RSP uCode to accomplish this.

### .fifo (e.g gspFast3D.fifo.o)
FIFO microcode uses a Queue (First in First Out) in RDRAM that is directly passed to the RDP.

### .xbus (e.g gspF3DEX2.xbus.o)
The XBUS is a physical connection that connects the RSP and RDP together on the chip. This allows passing data directly from the RSP to RDP without going through any additional steps such as using RDRAM.

### .dram (e.g gspFast3D.dram.o)
The DRAM method uses extensive use of RDRAM to store the RDP commands and requires work on the cpu to move the data to the RDP.

# IMEM and DMEM
RSP has its own 8kb of memory split into 2 chunks, one for assembly instructions (opcodes) and the other 4k for data. The Data portion was called DMEM (0x04000000 -> 0x04000FFF) and the Code portion was called IMEM (0x04001000 -> 0x04001FFF) [^2].

# RSPBOOT
RSPBOOT is a short piece of code to initialise/boot the RSP, the assembled `rspboot.o` file contains in the Official Nintendo64 SDK is 740bytes but as that contains extra object data when compiled into the final rom it only takes about 208bytes (e.g Mario64).

RSPBoot is included in pretty much all N64 games and is specified in the n64 development `spec` file normally after the codesegment.

In an example spec file:
```
include "codesegment.o"
include "$(ROOT)/usr/lib/PR/rspboot.o"
```

The rspboot ucode is loaded into IMEM at the beginning of each OSTask (e.g in `osSpTaskLoad`). The rspboot microcode is used to set a few initial register values, parse the Task header and then load the next microcode.

# CodeSegment.o
CodeSegment.o file is generated s part of the build process for many of the demos, it can technically be called anything but most of the games call this codesegment.o. The file is a result of linking all the source files together so it is the output of the Linker (LD).

# Microcode/uCode limitations
Instructions must fit in the 4KB IMEM memory region so this limits the microcode to 1,000 instructions available in memory at once (due to each instruction being 4bytes and the total IMEM is 4kb) [^4].

To get around this limitation code `overlays` can be used and will be discussed further on, however it is important to note that the use of code `overlays` has a negative performance impact.

# Display Lists
Display lists can be thought of as a set of commands (ucode) that can be used by the programmer to manipulate the RSP’s currently running microcode [^5].

# Graphical Binary Interface (GBI)
The graphics programmer controls the RSP from main game code using the GBI. 

So Display lists are created based on the commands listed in the GBI and are sent to the RSP to be interpreted by the loaded RSP Microcode.

So you could summarize that the purpose of the graphics RSP microcode is to implement the functionality required by the GBI.

#  Yoshitaka Yasumoto
 Yoshitaka Yasumoto is credited in many games as being the microcode programmer (e.g Yoshi’s story) but most games use his microcode without explicitly giving credit as it was part of the Official N64 SDK. 

If you search a N64 rom file for his name "Yoshitaka Yasumoto" you will likely find the microcode that he has written. This works for most games unless they used their own custom uCode.

#  References
[^1]: https://forum.beyond3d.com/threads/n64-rdp-rsp.15758/
[^2]: https://patater.com/gbaguy/day8n64.htm
[^3]: http://n64devkit.square7.ch/n64man/ucode/rspboot.htm
[^4]: https://www.docdroid.net/NXMlF3s/grucode.pdf#page=3 
[^5]: https://en.wikibooks.org/wiki/N64_Programming/Video_coprocessor 
[^6]: https://hylianmodding.com/Thread-A-comprehensive-guide-to-F3DZEX-F3DEX2-Display-Lists 
[^7]: https://level42.ca/projects/ultra64/Documentation/man/pro-man/pro25/index25.4.html 
[^8]: https://level42.ca/projects/ultra64/Documentation/man/n64man/ucode/gspF3DLP.Rej.html 

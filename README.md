# Mistix Hackpad

A 3-key macropad built around a Seeed XIAO RP2040, made for [Hack Club's Hackpad YSWS](https://hackpad.hackclub.com/) (Stardance). Custom PCB in KiCad, custom case in Tinkercad, and QMK firmware for media controls.

## Overview

Mistix Hackpad is my first ever hardware project – the first board design, the first CAD model, the first experience with flashing keyboard firmware. Something simple yet complete, from schematic, to routing, case design, and firmware.

The board features three mechanical switches directly connected to XIAO RP2040 (with no diode matrix, just one GPIO per switch), and QMK media-control keymap.

<img width="1332" height="537" alt="Screenshot 2026-09-07 195935" src="https://github.com/user-attachments/assets/4cb0267a-1e70-4499-b763-27bb7a783508" />

## PCB Design

Designed from scratch in KiCad. The XIAO RP2040 is wired directly to 3 push switches (one GPIO pin per switch — pins 9, 10, and 11), with all switches sharing a common GND. Since this is a direct-pin matrix (no diodes needed), the schematic and routing stayed pretty simple, which made it a good first PCB to learn on.

Gerbers and drill files are exported and included in the repo, in the production folder.

<img width="1592" height="678" alt="image" src="https://github.com/user-attachments/assets/6f4aa69a-68ad-4131-a1f1-16bb39c69563" />

## Case Design

The casing was made using Tinkercad, with the casing being divided into two sections of the bottom tray and the top plate. It was done following the typical case design tutorial without making any changes to keep it simple:

Bottom tray: 77.4mm x 39mm base slab with 3mm thickness having a 10mm wall frame (10mm tall), inner cavity for accommodating the PCB (57.4mm x 19mm), four corner mounting holes (2.9mm in diameter with 5mm from the edge), and USB-C hole.
Top plate: 77.4mm x 39mm slab (3mm thick) with three switch holes (14mm x 14mm Cherry MX-sized) along with the same four corner mounting holes to make sure that it aligns with the bottom tray.

<img width="1048" height="592" alt="image" src="https://github.com/user-attachments/assets/8e4d8662-56ae-4256-96a6-a419907b371f" />

## Firmware

Built using QMK. The board is configured as a direct-pin matrix (no diodes) on GP9, GP10, and GP11. Firmware source is in `Firmware/`, and the compiled `.uf2` file is included in `Production/`.

Current keymap:

| Switch | Function        |
| ------ | --------------- |
| 1      | Play / Pause    |
| 2      | Volume Down     |
| 3      | Volume Up       |

## What I Learned

This was my first time working with most of the tools involved:

| Area                            |
| --------------------------------|
| KiCad schematic + PCB design    |
| PCB routing                     |
| Footprint assignment            |
| Gerber / drill file export      |
| CAD modelling in Tinkercad      |
| QMK firmware setup & compiling  |
| Direct-pin (diodeless) matrix   |

This is all very new to me, especially QMK and firmwares, but my aim was to try and do the whole thing, rather than waiting to understand everything before doing anything at all.

## Why I Built It

Honestly, I wanted an excuse to finally learn how hardware is made and not just look at video tutorials on it. A 3-key macropad seemed a perfect choice to me in that case: small enough so that I could finish it but still making me go through all the processes a larger project would entail, namely schematic, PCB, CAD, firmware, etc.

None of these programs was known to me before working with it. KiCad, Tinkercad, QMK – all the above mentioned were new for me, and therefore learning everything right away and spending much time on it, carrying out many checks and not missing any of the stages thinking I know how to work with it. But it was the point of it all – to undergo the whole process of creation, and not postpone it.

In first place, it was the question of obtaining certain skills that will be useful for me in the future when ill be wokring on more complicated projects as of now I have already undergone this whole process from the schematic to the final product.

## Project Structure

Path | Contents
--- | ---
`CAD/` | MistixHackpad.stp
`Firmware/` | QMK firmware project
`Firmware/keymap/` | Default keymap
`Firmware/keybooard.json` | QMK keyboard definition
`Ki-CAD-LIBS/` | Custom KiCad footprints
`Ki-CAD-LIBS/footprints.pretty/` | Footprint library folder
`Ki-CAD-LIBS/SK6812MINI-E.kicad_mod` | RGB LED footprint
`Ki-CAD-LIBS/XIAO_RP2040.kicad_mod` | XIAO RP2040 footprint
`PCB/` | KiCad PCB, project, and schematic files
`Production/` | STL files, compiled firmware, and Gerbers
`Production/bottom.stl` | Case bottom tray
`Production/Top.stl` | Case top plate
`Production/firmware.uf2` | Compiled firmware
`Production/gerber-drill.zip` | Fabrication gerbers + drill files
`bom.csv` | Machine-readable parts list
`.gitattributes` | Git attributes
`.gitignore` | Git ignore rules
`README.md` | Project documentation

## Current Status

Schematic, PCB routing, Gerbers, case model, and firmware are all finished and in the repo. Next step is getting the project approved through Stardance, then making it IRL.

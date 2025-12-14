# Modular Reconfigurable Pedalboard
A modular, reconfigurable guitar/bass pedalboard designed as a **universal base** for **interchangeable effect modules**.  
Current version includes two analog effect circuits: an **MXR-style Distortion+ inspired clone** and a **silicon Fuzz Face–inspired fuzz**.

---

<img src="fotos%20pedal/WhatsApp%20Image%202025-12-11%20at%2019.27.27.jpeg" alt="Pedalboard photo" width="350">

---

## Features (current)

- A modular board capable of hosting **two 8 pin effect modules** simultaneously
- Two analog effect modules included:
  - **MXR-style distortion** (Distortion+/D+ family inspiration)
  - **Silicon Fuzz Face–inspired fuzz**
- Each module supports **up to two PCB-mounted potentiometers** for onboard control (e.g., Gain/Level, Fuzz/Volume)
- Designed for common use with string instruments, such as **electric guitars** or **basses**
- Fully **customizable** and **open-source** for public access

---

## Repository structure

- `PlacaGeral/` — The **main board** (the “placão”): carrier/backplane PCB that hosts the modules and concentrates the shared wiring.
- `Pedais/` — The **effect modules** (schematics/PCB files for Dizzy and Amorphous, and future modules).
- `Modelos pedal/` — Mechanical assets (e.g., templates, outlines, 3D/visual models, and design references).
- `fotos pedal/` — Build photos and progress shots used in the README and documentation.
  
---

## Included effect modules

### 1) **Dizzy** - Silicon Fuzz Face–inspired fuzz 

<img src="fotos%20pedal/WhatsApp%20Image%202025-12-11%20at%2019.24.14.jpeg" alt="dizzy" width="350">

A two-transistor silicon fuzz, implemented with a **negative-ground** power scheme for easy integration with other pedal models.
Great for raw, dirty and aggressive tones.

This module is nicknamed **Dizzy**, referencing the fuzz’s naturally **psychedelic, dizzy aesthetic**.

Reference / inspiration:
- Fuzz Central (Fuzz Face): https://fuzzcentral.ssguitar.com/fuzzface.php

### 2) **Amorphous** - MXR-style distortion (Distortion+ inspired)


<img src="fotos%20pedal/WhatsApp%20Image%202025-12-11%20at%2019.26.20.jpeg" alt="amorph" width="350">

A classic op-amp gain stage with germanium diode clipping (the “raw” distortion character).  
Useful for gritty tones.  

This module is nicknamed **Amorphous**, referencing how distortion/clipping turns a clean waveform into a denser, less-defined shape.

Reference / inspiration:
- Electrosmash analysis: https://www.electrosmash.com/mxr-distortion-plus-analysis

## The **Main Board**

The **PlacaGeral** is the carrier PCB that turns this project into a modular system. In practice, it works like a small “backplane” for pedals:

- Provides **two module slots** (two 8-pin effect modules at the same time)
- Routes **audio I/O** and keeps a consistent grounding scheme across modules
- Distributes **9V DC power** to the modules (the main board is **center-positive** oriented — double-check before powering)
- Offers a standardized mechanical/electrical base so modules can be swapped without rewiring the whole pedalboard

> ⚠️ Many common pedal supplies are **center-negative**. Do **not** plug a standard center-negative supply into a center-positive board without an adapter/inverter — unless you want to release the magic smoke (and smell something funny).

<img src="fotos%20pedal/WhatsApp%20Image%202025-12-02%20at%2018.11.16.jpeg" alt="amorph" width="350">

---

## Cartridge (module holder)

Each effect module is mounted on a removable 3d printed Gameboy inspired **cartridge**, which provides mechanical support and keeps the 8-pin module interface consistent across pedals.

This cartridge was adapted from an existing model available at **(link)** and then modified for this project (fit/clearance/alignment), including:
- alignment tweaks in order to support pedals PCBs.
- clearance changes to avoid collisions with tall components, and parts of the main board structure

Reference / inspiration:
 - (link)

---

## Power & safety notes

- **Verify supply voltage (9V DC) and polarity** before connecting any power source.
- Before first power-up:
  - Confirm electrolytic capacitor orientation.
  - Verify power supply polarity: the main board is **center-positive** oriented.
 
## 3D printed structures notes

It was necessary to modify the case of the **Main board** to accommodate the final board layout.
 
## Electronics hardware notes

During initial bring-up, the main board required a small routing correction: 
 - To properly route the **effect IN/OUT** of each module, it is necessary **cut two traces per pedal** (one affecting the input path and one affecting the output path).  
 - To fix the audio routing, the board was **rewired** (trace cuts + jumper wires) for each module’s input and output.
 - Additionally, the two buffers were removed because they were not handling the signal swing correctly and ended up clipping the **negative half-cycle** of the waveform. This change restored a more symmetric signal path.
This was a quick rework step applied on the assembled board and will be addressed in the next PCB revision.

<img src="fotos%20pedal/WhatsApp%20Image%202025-12-11%20at%2019.14.57.jpeg" alt="amorph" width="350">
 
## Credits / Contributions

- **João Neto** — Pedal testing and validation **before** assembling the PCBs (pre print tests).
- **Guilherme Santos** — Pedal testing and validation **before** assembling the PCBs (pre print tests); **PCB design**, **assembly**, and **final testing** of the system.
- **Romulko Soli** — **3D modeling** (enclosure/mechanical models).


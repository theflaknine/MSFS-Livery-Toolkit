# MSFS Livery Toolkit

A free Windows tool for creating **Microsoft Flight Simulator** liveries — scaffold a livery, prepare and flag its artwork, and compile sim-ready assets, all from one app.

Supports MSFS 2020 and 2024, across all three package structures (2020 monolithic / DDS, 2024 monolithic / KTX2, and 2024 modular / KTX2).

> This repository is the **public home** for the toolkit — downloads, issue tracking, and documentation. The application source is maintained privately.

## Download

Grab the latest portable release from the [**Releases**](https://github.com/theflaknine/MSFS-Livery-Toolkit/releases) page. No installer — unzip and run.

**Requirements**
- Windows 11 (64-bit)
- Microsoft Flight Simulator 2020 and/or 2024
- The matching MSFS SDK (installed via the sim's Dev Mode) — needed to compile textures
- [MSFSLayoutGenerator](https://github.com/HughesMDflyer4/MSFSLayoutGenerator/releases)

## Documentation

Full user guide: **https://theflaknine.github.io/MSFS-Livery-Toolkit/**

## Found a bug or have an idea?

Please [open an issue](https://github.com/theflaknine/MSFS-Livery-Toolkit/issues). Bug reports are most useful when they include your sim generation (2020 / 2024), the base aircraft, and steps to reproduce.

## Third-party components

The app bundles a small number of open-source components, listed in its in-app **About** panel. Notably, texture extraction uses [`ooz`](https://github.com/powzix/ooz) (GPL-3) as a separate bundled program; its complete source and license ship inside every release package.

# MSFS Livery Toolkit

A free Windows tool for creating **Microsoft Flight Simulator** liveries; build the full livery file and folder structure, generate placeholder images ready for edting, prepare and flag its artwork, then compile sim-ready assets, all from one app.

Supports MSFS 2020 and 2024, across all three package structures (2020 monolithic / DDS, 2024 monolithic / KTX2, and 2024 modular / KTX2).

> This repository is the **public home** for the toolkit, including downloads, issue tracking, and documentation. The application source is maintained privately.

## A message from the developer
**Hobbyist Built:** I am a livery painter, not a professional software developer. This toolkit was built to automate the tedious backend chores of package layout so we can all spend more time creating.

**AI-Assisted Architecture:** Because I lacked the coding experience to build a full Windows application from scratch, I used a personally funded Claude Pro subscription to bridge the gap.

**Human-Driven Logic:** This is not unthinking "AI slop." Every workflow step, simulator profile rule, and configuration logic choice was explicitly designed by me based on real flight-sim SDK behavior and manually verified at every milestone.

**Always Free:** Leveraging these modern tools made it possible to build a polished desktop utility in my spare time and release it completely free to the flight simulation community. I will never monetize this app (besides entirely optional donations) or lock functionality behind a paid-for tier.

## Download

(COMING SOON) Grab the latest portable release from the [**Releases**](https://github.com/theflaknine/MSFS-Livery-Toolkit/releases) page. No installer, simply unzip and run `MsfsLiveryToolkit.App.exe`. You'll probably get a Windows warning about an unsigned exe, so you'll need to click **More Info** > **Run Anyway** to proceed, if you are comfortable to do so. See **https://theflaknine.github.io/MSFS-Livery-Toolkit/trust-and-safety.html** for more details on unsigned applications.

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

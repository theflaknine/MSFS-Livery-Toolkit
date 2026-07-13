---
title: Compiling
layout: default
nav_order: 4
---

# Compiling your package
{: .no_toc }

1. TOC
{:toc}

---

The **Compile** page turns your source PNG artwork into sim-ready files (DDS or KTX2) and builds your distributable package.

{: .warning }
> **Compilation drives the live simulator.** Texture compilation uses the official MSFS SDK compiler, which opens and closes your Microsoft Flight Simulator once for each livery being compiled. Don't start a build while you're using the sim, or if you want to avoid it launching in the background.

## Running a build

1. Click **Compile**. The app locks navigation for the whole build to protect your data.
2. A progress bar tracks status (e.g. "Building livery N of M").
3. On success, use the quick actions to **Open build log** or **Open built package folder**.

If you click **Cancel**, the toolkit stops its build chain, but it won't force-terminate a simulator run the SDK has already started.

## Other build actions

- **Update layout.json only** — regenerates just `layout.json` (no texture recompile, no sim launch). The page shows that file's last-modified time. Every full compile also regenerates `layout.json` from scratch, so file sizes and verification hashes always stay in sync.
- **Launch Microsoft Flight Simulator** — starts the sim directly (fast-launch, skipping intro videos) to test your livery in-game. If both a Steam and an MS Store copy of the required generation are installed, the app asks which to launch.

## Sim-running warning

If Microsoft Flight Simulator is already running for your project's generation, the Work, Compile, and Project pages show a dismissible warning — editing or compiling files the sim has open can cause instability. It's a soft warning you can dismiss and proceed past, not a hard block.

## Package metadata

Use the **Project details** screen to set the top-level manifest fields for your package:

- Project title
- Content type and aircraft manufacturer
- Creator name and version (one-click Major / Minor / Patch bumps)

If you hand-edit `package_version`, `manufacturer`, or `creator` directly in the package's `manifest.json`, the app picks up your change the next time the project is opened and keeps both in sync.

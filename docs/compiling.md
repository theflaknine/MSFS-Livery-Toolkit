---
title: Compiling
layout: default
nav_order: 5
---

# Compiling your package
{: .no_toc }

1. TOC
{:toc}

---

The **Compile** page turns your source PNG artwork into sim-ready files (DDS or KTX2) and builds your livery package ready to include in your community folder.

{: .warning }
> **Compilation drives the live simulator.** Texture compilation uses the official MSFS SDK compiler, which opens and closes your Microsoft Flight Simulator once for each livery being compiled. Don't start a build while you're using the sim, or if you want to avoid it launching in the background.

## Running a build

1. Click **Compile**. The app locks navigation for the whole build to protect your data.
2. A progress bar tracks status (e.g. "Building livery N of M").
3. On success, use the quick actions to **Open build log** or **Open built package folder**.

If you click **Cancel**, the toolkit stops its build chain, but it won't force-terminate a simulator run the SDK has already started.

## Other build actions

- **Update layout.json only:** regenerates just `layout.json` (no texture recompile, no sim launch). The page shows that file's last-modified time. Every full compile also regenerates `layout.json` from scratch, so file sizes and verification hashes always stay in sync.
- **Launch Microsoft Flight Simulator:** starts the sim directly (fast-launch, skipping intro videos) to test your livery in-game. If both a Steam and an MS Store copy of the required generation are installed, the app asks which to launch.

## Warnings that do not block compiling

The Compile page can show two warning cards above the build button. Neither one stops you compiling, but
both are worth reading before you do.

- **Missing textures.** Lists any livery with textures that have no local image and no fallback reaching a
  compiled copy. Those will render as a pink checkerboard in the simulator. Open **Edit fallback** and use
  **Check texture coverage** to see the full list and fix it.
- **No matching configuration.** Lists any livery on a modular aircraft whose tags do not match any
  configuration the aircraft offers. The build will succeed, but the livery will never appear in the
  simulator with nothing to say why. Change which configurations it appears under on its **Availability**
  tab on the Liveries page.

## Sim-running warning

If Microsoft Flight Simulator is already running for your project's generation, the Work, Compile, and Project pages show a dismissible warning - editing or compiling files the sim has open can cause instability. It's a soft warning you can dismiss and proceed past, not a hard block.

If you hand-edit `package_version`, `manufacturer`, or `creator` directly in the package's `manifest.json`, the app picks up your change the next time the project is opened and keeps both in sync.

---
title: Configuration
layout: default
nav_order: 6
---

# Configuration

The **Settings** page holds the settings the toolkit needs to find your aircraft and drive the SDK.

## SDK and tool paths

- **MSFS 2020 SDK** and **MSFS 2024 SDK:** the app auto-detects the default install locations; set at least one, matching the aircraft you intend to build for.
- **MSFSLayoutGenerator:** used to regenerate `layout.json` on every build. A copy is **bundled with the app and used automatically**, so you don't need to download or set anything. Set a path here only if you want to use your own copy (for example a [newer release](https://github.com/HughesMDflyer4/MSFSLayoutGenerator/releases)).
- **2020 compile method:** **MSFS SDK**, or **texconv**, a bundled encoder (Microsoft DirectXTex, MIT-licensed) that compiles MSFS 2020 liveries with no SDK or simulator installed at all. The SDK is used unless you choose texconv, which is chosen for you if no 2020 SDK is found.

## Steam vs. MS Store

A toggle that tells the toolkit which storefront copy of MSFS to drive. It controls the `-forcesteam` flag passed to the SDK build tool, and which copy the build screen's **Launch** action starts on a machine with both installed.

{: .warning }
> **The Steam build path is untested.** I only own an MS Store copy of MSFS, so this option has never been verified against a real Steam install; only MS Store is confirmed working. If you hit a problem while using it, please [open an issue on GitHub](https://github.com/theflaknine/MSFS-Livery-Toolkit/issues/new) and attach your session log file (Settings → Diagnostics → **Open session log file**).

## 16-bit textures ##

When extracting source artwork from an aircraft KTX2 or DDS file, this option ensures that if the source files have 16-bit color depth then that detail is preserved in the corresponding PNG file. It is recommended to leave this option on.

## Defaults

- **Default creator name:** pre-fills the manifest `creator` field and, for modular aircraft, the `liveries\<creator>` folder name. Editable per livery afterwards.
- **Default output location:** the parent folder pre-filled when you create a new project.
- **Projects root folder:** where each project's workspace subfolder is created.
- **Default paintkit folder:** the parent folder pre-filled on the [Paintkit Builder]({{ '/paintkit-builder.html' | relative_url }}) page. A folder named after the aircraft is created inside it for each build, and you can change the location per build.

## Aircraft source folders

The list of folders scanned for base aircraft. Add them with **Add folder…**. Note that your MSFS Community folders should be detected automatically, there is no need to manually add them.

## Texture exclude list

This list excludes matching text strings from the texture list when you add a livery or add textures, to filter out textures that are unlikely to be required for livery artists, for example texture files containing the string "tire" or "gauge". You may edit this list as required, and reset to default if needed.

## 3D viewer

**Load the aircraft model automatically** decides whether the [Workspace]({{ '/workspace.html' | relative_url }}) loads the aircraft into its viewport by itself when a project opens or you change livery:

- **Off**: select **Load aircraft model** yourself.
- **Local aircraft only**: aircraft on your own drives load straight away.
- **Local aircraft, and VFS aircraft when the VFS is connected**: stock and Marketplace aircraft load too, if the VFS was connected when the project opened.

Loading reads every model file of the aircraft, which can take several seconds on a large one; the rest of the app stays usable meanwhile. An aircraft the simulator protects never loads.

## Appearance

**Monochrome icons** shows the Workspace's icons in the text colour instead of coloured by type.

## Diagnostics

**Open session log file** opens the log of the current run. Attach it when you report a problem.

## About

The **About** panel lists every bundled third-party component and its license, including the GPL-3 decompressor used only for the compressed-texture extraction case. The full license texts ship in `THIRD-PARTY-NOTICES.txt` and the `licenses` folder beside the launcher, and `LICENSE.txt` there holds the terms of use for the app itself.

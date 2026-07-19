---
title: Configuration
layout: default
nav_order: 5
---

# Configuration

The **Settings** page holds the settings the toolkit needs to find your aircraft and drive the SDK.

## SDK and tool paths

- **MSFS 2020 SDK** and **MSFS 2024 SDK:** the app auto-detects the default install locations; set at least one, matching the aircraft you intend to build for.
- **MSFSLayoutGenerator:** used to regenerate `layout.json` on every build. A copy is **bundled with the app and used automatically** — you don't need to download or set anything. Set a path here only if you want to use your own copy (e.g. a [newer release](https://github.com/HughesMDflyer4/MSFSLayoutGenerator/releases)).

## Steam vs. MS Store

A toggle that tells the toolkit which storefront copy of MSFS to drive. It controls the `-forcesteam` flag passed to the SDK build tool, and which copy the Compile page's **Launch** action starts on a machine with both installed.

{: .warning }
> **The Steam build path is untested.** The developer only owns an MS Store copy of MSFS, so this option has never been verified against a real Steam install, only MS Store is confirmed working. If you hit a problem while using it, please [open an issue on GitHub](https://github.com/theflaknine/MSFS-Livery-Toolkit/issues/new) and attach your session log file (Settings → Diagnostics → **Open session log file**).

## 16-bit textures ##

When extracting source artwork from an aircraft KTX2 or DDS file, this option ensures that if the source files have 16-bit color depth then that detail is preserved in the corresponding PNG file. It is recommended to leave this option on.

## Defaults

- **Default creator name:** pre-fills the manifest `creator` field and, for modular aircraft, the `liveries\<creator>` folder name. Editable per livery afterwards.
- **Default output location:** the parent folder pre-filled when you create a new project.
- **Projects root folder:** where each project's workspace subfolder is created.

## Aircraft source folders

The list of folders scanned for base aircraft. Add them with **Add folder…**. Note that your MSFS Community folders should be detected automatically, there is no need to manually add them.

## Texture exclude list

This list excludes matching text strings from the Texture Selector, to filter out textures that are unlikely to be required for livery artists, for example texture files containing the string "tire" or "gauge". You may edit this list as required, and reset to default if needed.

## About

The **About** panel lists every bundled third-party component and its license, including the GPL-3 decompressor used only for the compressed-texture extraction case.

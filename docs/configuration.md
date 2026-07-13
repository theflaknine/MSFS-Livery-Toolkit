---
title: Configuration
layout: default
nav_order: 5
---

# Configuration

The **Config** page holds the settings the toolkit needs to find your aircraft and drive the SDK.

## SDK and tool paths

- **MSFS 2020 SDK** and **MSFS 2024 SDK** — the app auto-detects the default install locations; set at least one, matching the aircraft you intend to build for.
- **MSFSLayoutGenerator** — used to regenerate `layout.json` on every build. [Download it here](https://github.com/HughesMDflyer4/MSFSLayoutGenerator/releases).

## Steam vs. MS Store

A toggle that tells the toolkit which storefront copy of MSFS to drive. It controls the `-forcesteam` flag passed to the SDK build tool, and which copy the Compile page's **Launch** action starts on a machine with both installed.

## Defaults

- **Default creator name** — pre-fills the manifest `creator` field and, for modular aircraft, the `liveries\<creator>` folder name. Editable per livery afterwards.
- **Default output location** — the parent folder pre-filled when you create a new project.
- **Projects root folder** — where each project's workspace subfolder is created.

## Aircraft source folders

The list of folders scanned for base aircraft. Add them with **Add folder…**, or click **Detect Community folders** to find your Community / add-on-linker locations automatically.

## About

The **About** panel lists every bundled third-party component and its license, including the GPL-3 decompressor used only for the compressed-texture extraction case.

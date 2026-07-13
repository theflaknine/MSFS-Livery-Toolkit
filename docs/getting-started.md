---
title: Getting started
layout: default
nav_order: 2
---

# Getting started
{: .no_toc }

1. TOC
{:toc}

---

## First-run setup

Before you can discover aircraft or compile anything, open the **Config** page and set up:

- **Aircraft source folders** — the folders scanned for installed base aircraft. Use **Detect Community folders** to find them automatically, or **Add folder…** to point at a Community / add-on-linker location manually.
- **At least one MSFS SDK path** (2020 or 2024). The app auto-detects the default install locations; confirm or correct them here.

If either is missing, the Home page shows a **"Let's get you set up"** banner with a shortcut to Settings, and *Discover aircraft* stays disabled until it's resolved.

## Creating a project

On the **Home** page:

1. Click **Discover aircraft** to populate the base-aircraft list, then pick one. Search by title, manufacturer, or folder name. A colour-coded **profile badge** shows whether it's 2020 Mono, 2024 Mono, or 2024 Modular.
2. Name your project.
3. Confirm the **output location**. The app suggests a folder name following MSFS naming conventions (`<company>-aircraft-<name>-livery-<project>`), but it's fully editable, and a live preview shows the exact path that will be created.
4. Click **Create**. This makes an empty project with no liveries yet.
5. Switch to **Edit liveries** and click **Add livery** to scaffold your first one.

## The two locations of a project

Every project lives in two places on disk:

- **Workspace** — holds the project save file and your loose, editable PNG artwork. Safe to move or rename; the app always finds the project by wherever the save file currently sits.
- **Deployment target** — the final compiled package the simulator reads.

Open either at any time from the **Open folder in Windows Explorer** shortcuts (Base Aircraft / Project / Built Package) in the navigation pane footer, next to **Save**.

## Opening and pinning projects

The Home dashboard keeps two lists:

- **Pinned projects** — projects you've starred, kept at the top permanently.
- **Recent projects** — an automatically maintained, capped history. Clear unpinned recents or all history with the **Clear** buttons.

Each row shows a small thumbnail preview derived from the project's first livery.

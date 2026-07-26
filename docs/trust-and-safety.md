---
title: Trust & safety
layout: default
nav_order: 7
---

# Trust & safety
{: .no_toc }

This page exists because the app triggers a few things worth explaining honestly: an "Unknown publisher" warning from Windows, and a couple of small extra helper programs (`ooz.exe`, `texconv.exe`) sitting alongside the main program. Here's exactly what's going on with all of it, and what the app actually does on your machine.

1. TOC
{:toc}

---

## Why Windows warns about it

The toolkit isn't code-signed, so Windows SmartScreen will flag it as coming from an "Unknown publisher" the first time you run it. That's not a statement about what the app does — it's purely about the certificate.

Code-signing certificates that actually clear SmartScreen (EV certificates) cost real money every year and are aimed at commercial software. This is a free hobby project built and maintained by one person, so it isn't signed. That's the whole story, there's no functional difference between a signed and unsigned build of the same code.

If you'd rather verify the download yourself before running it, every release has a published SHA-256 hash (see [Verifying a download](#verifying-a-download) below) — check it against what you downloaded and you know you have exactly the file that was published, byte for byte.

## What the app actually touches on your PC

- **Your installed aircraft:** read-only. The toolkit reads a base aircraft's files to find its textures and registration data; it never writes into a base aircraft's own folders.
- **Your project folder:** the only place it writes: your chosen workspace (loose PNG artwork + project file) and your chosen output/deployment folder.
- **The official MSFS SDK tools already on your machine:** compiling a livery hands your artwork to Microsoft's own `fspackagetool.exe` (installed with the SDK via the sim's Dev Mode) and the community [MSFSLayoutGenerator](https://github.com/HughesMDflyer4/MSFSLayoutGenerator) tool. The toolkit doesn't do its own custom compiling — it drives the same official tools you'd otherwise run by hand, and that briefly opens and closes Microsoft Flight Simulator itself, the same way those tools always have.

Nothing outside those three areas.

## Does it phone home?

No. There is no network code in the app at all, not a hidden one, not an optional one. Every place that looks like a "link" (the Help button, Donate, the SDK download link) is the app asking Windows to open your normal web browser to a page, exactly like clicking a link in a text editor. The app itself never makes an HTTP request, never uploads anything, and collects no telemetry or usage data of any kind.

## What is `ooz.exe`?

Most base-aircraft textures decode with a fully in-app, built-in image decoder and no extra program involved. A minority of newer MSFS aircraft compress their textures with a format the built-in decoder can't unpack on its own. For that specific case, the app calls a small, separate, open-source helper program: [`ooz`](https://github.com/powzix/ooz) (licensed GPL-3).

A few things worth knowing about it:

- **It's a genuinely separate program**, launched as its own process the same way the app launches the official MSFS SDK tools, it is never linked into or combined with the app's own code.
- **It only ever touches local files you already have**, the base aircraft texture you asked to extract, and the PNG it writes out. No network access, no other purpose.
- **Its complete source code ships inside every release**, alongside the license — you don't have to trust a compiled binary blindly; you (or anyone) can read exactly what it does, or rebuild it yourself from that source and compare.
- **It's used narrowly**, only when you explicitly choose "Extract from base" on a texture that needs it. Every other feature in the app never touches it.

## What is `texconv.exe`?

MSFS 2020 liveries can optionally be compiled without the MSFS 2020 SDK or simulator installed at all, using a small texture encoder instead of the usual official SDK tool. When that's turned on in Settings (off by default, or automatic if you don't have the 2020 SDK installed), the app calls texconv: Microsoft's own [DirectXTex](https://github.com/microsoft/DirectXTex) texture converter, MIT licensed, run as a separate process. Same arm's-length pattern as `ooz.exe` above.

A few things worth knowing about it:

- **It's Microsoft's own official texture-conversion tool**, part of the DirectXTex project, used unmodified.
- **It's off by default.** The app compiles through the real MSFS SDK/simulator unless you explicitly turn this on, or the 2020 SDK isn't installed, in which case it's the only option since there's nothing else to compile with.
- **It only ever touches your project's own texture files**: the source artwork you're compiling and the DDS files it writes out. No network access.
- **A few small Microsoft Visual C++ runtime files ship alongside it** so it runs standalone. These are standard, widely distributed system components, not anything specific to this app.

## About the source code

The application's source isn't public, this is still a small, early hobby project, not something ready for outside contributions yet. What *is* public and welcomes scrutiny: this documentation, the [issue tracker](https://github.com/theflaknine/MSFS-Livery-Toolkit/issues), and every third-party component the app bundles (listed with its license in the in-app **About** panel). If something here doesn't add up or you'd like more detail on a specific behavior, please open an issue and I'll be happy to answer.

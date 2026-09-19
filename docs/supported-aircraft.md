---
title: Supported aircraft
layout: default
nav_order: 2.5
---

# Supported aircraft
{: .no_toc }

MSFS aircraft come in several shapes, and what the toolkit can do depends on which one you are painting. This page shows every main feature against the six kinds of aircraft you are likely to meet.

1. TOC
{:toc}

## The six kinds of aircraft

The toolkit sorts every aircraft by two things: which simulator it was built for, and how it is put together.

- **2020 mono**: an aircraft built for MSFS 2020. Its textures are DDS files, and each livery is its own aircraft entry that borrows the model from the base aircraft.
- **2024 mono**: an aircraft built for MSFS 2024 in the same traditional way. Its textures are KTX2 files.
- **2024 modular**: an MSFS 2024 aircraft built from parts, with configurations (for example floats, skis or a cargo pod) that a livery can be limited to.

*"Mono" is short for monolithic, which is what the toolkit calls any aircraft that isn't modular.* The profile badge in **Discover aircraft** tells you which kind an aircraft is.

Each of the three can also be **encrypted**: some stock and Marketplace aircraft are partly protected by the simulator, so their configuration files and highest-detail 3D models can't be read. The Livery Toolkit never decrypts, bypasses or reverse engineers protected files. It reads only the files the simulator itself leaves readable, such as textures and livery and texture configuration files, the same files any livery artist works from. That is why some features, like 3D previews and UV maps, aren't available for these aircraft.

In the app, encrypted aircraft are marked with a padlock and described as *protected by the simulator*.

## Feature matrix

**Yes** means the feature works. **Partly** means it works with a limit, explained in the notes below the table. **No** means the feature isn't available for that kind of aircraft.

| Feature | 2020 mono | 2024 mono | 2024 modular | 2020 mono, encrypted | 2024 mono, encrypted | 2024 modular, encrypted |
|---|---|---|---|---|---|---|
| **Finding and setting up** | | | | | | |
| Listed in Discover aircraft | Yes | Yes | Yes | No <sup>1</sup> | No <sup>2</sup> | Yes, with a padlock |
| Create projects and liveries | Yes | Yes | Yes | No | No | Yes |
| Stock and Marketplace aircraft | Untested <sup>3</sup> | Yes | Yes | No | No | Yes |
| Proper aircraft name in the list | Yes | Yes | Yes | No | No | Partly <sup>4</sup> |
| **Textures** | | | | | | |
| Texture list and type labels | Yes | Yes | Yes | No | No | Partly <sup>5</sup> |
| Extract a texture from the aircraft to PNG | Yes | Yes | Yes | No | No | Yes |
| Placeholder images | Yes | Yes | Yes | No | No | Yes |
| Edit texture fallbacks | Yes | Yes | Yes | No | No | Yes |
| Check texture coverage (pink checkerboard warning) | Yes | Yes | Yes | No | No | No <sup>6</sup> |
| Extract UV map | Yes | Yes | Yes | No | No | No |
| **Livery settings** | | | | | | |
| Details (title, ATC id and other fields) | Yes | Yes | Yes | No | No | Yes |
| Registration number | Yes <sup>7</sup> | Yes <sup>7</sup> | Yes <sup>7</sup> | No | No | Partly <sup>8</sup> |
| Availability (which configurations a livery appears under) | Not needed | Not needed | Yes | No | No | Partly <sup>9</sup> |
| **Previews and thumbnails** | | | | | | |
| 3D preview, including click to add a texture | Yes | Yes | Yes | No | No | No |
| Rendered thumbnails (experimental) | Yes | Yes | Yes | No | No | No |
| Placeholder thumbnails, or your own images | Yes | Yes | Yes | No | No | Yes |
| **Paintkit Builder** | | | | | | |
| Layered paintkit with albedo, composite and normal layers | Yes | Yes | Yes | No | No | Yes |
| UV wireframe and paintable-area layers | Yes | Yes | Yes | No | No | No |
| 3D paintkit (experimental) | Yes | Yes | Yes | No | No | No |
| **Compiling** | | | | | | |
| Compile with the MSFS SDK | Yes | Yes | Yes | No | No | Yes |
| Compile without the SDK installed | Yes <sup>10</sup> | No | No | No | No | No |

## Notes

1. **Encrypted MSFS 2020 aircraft are not supported.** MSFS 2020 protects its aircraft differently, and I have not been able to test one.
2. **Encrypted 2024 mono aircraft are not listed.** Too little of them can be read to build a working livery. The Discover message tells you how many aircraft were left out for this reason.
3. **Stock and Marketplace aircraft are read from the simulator's Virtual File System** while MSFS is running. This is tested with MSFS 2024 only.
4. **An encrypted aircraft shows its folder name** until you pick its real name from the list MSFS 2024 reports while it's running. Your choice is remembered.
5. **The texture list for an encrypted aircraft is built from its lower-detail models**, because the highest-detail ones can't be read. A texture used only by the highest-detail model may appear under the aircraft's other texture folders instead.
6. **The files that say which textures each configuration needs are protected**, so the check can't tell what is missing. Check the livery in the simulator for pink areas instead.
7. **Only on aircraft that can display a registration.** The Registration number tab tells you when an aircraft can't.
8. **Offered on every encrypted aircraft**, because the files that show whether an aircraft can display a registration are protected. It works where the aircraft supports it.
9. **Configurations are shown by their folder names**, because the names you see in the simulator are stored in protected files.
10. **MSFS 2020 only**, using a bundled texture converter instead of the SDK and the simulator. Turn it on in Settings.

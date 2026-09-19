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

<table class="aircraft-matrix">
  <thead>
    <tr class="matrix-groups">
      <th scope="col" rowspan="2">Feature</th>
      <th scope="colgroup" colspan="3">Not encrypted</th>
      <th scope="colgroup" colspan="3" class="matrix-encrypted-start">Encrypted</th>
    </tr>
    <tr>
      <th scope="col">2020 mono</th>
      <th scope="col">2024 mono</th>
      <th scope="col">2024 modular</th>
      <th scope="col" class="matrix-encrypted-start">2020 mono</th>
      <th scope="col">2024 mono</th>
      <th scope="col">2024 modular</th>
    </tr>
  </thead>
  <tbody>
    <tr class="matrix-section"><th colspan="7" scope="colgroup">Finding and setting up</th></tr>
    <tr><th scope="row">Listed in Discover aircraft</th><td>Yes</td><td>Yes</td><td>Yes</td><td>No <sup>1</sup></td><td>No <sup>2</sup></td><td>Yes <sup>11</sup></td></tr>
    <tr><th scope="row">Create projects and liveries</th><td>Yes</td><td>Yes</td><td>Yes</td><td>No</td><td>No</td><td>Yes</td></tr>
    <tr><th scope="row">Stock and Marketplace aircraft</th><td>Untested <sup>3</sup></td><td>Yes</td><td>Yes</td><td>No</td><td>No</td><td>Yes</td></tr>
    <tr><th scope="row">Proper aircraft name in the list</th><td>Yes</td><td>Yes</td><td>Yes</td><td>No</td><td>No</td><td>Partly <sup>4</sup></td></tr>
    <tr class="matrix-section"><th colspan="7" scope="colgroup">Textures</th></tr>
    <tr><th scope="row">Texture list and type labels</th><td>Yes</td><td>Yes</td><td>Yes</td><td>No</td><td>No</td><td>Partly <sup>5</sup></td></tr>
    <tr><th scope="row">Extract a texture from the aircraft to PNG</th><td>Yes</td><td>Yes</td><td>Yes</td><td>No</td><td>No</td><td>Yes</td></tr>
    <tr><th scope="row">Placeholder images</th><td>Yes</td><td>Yes</td><td>Yes</td><td>No</td><td>No</td><td>Yes</td></tr>
    <tr><th scope="row">Edit texture fallbacks</th><td>Yes</td><td>Yes</td><td>Yes</td><td>No</td><td>No</td><td>Yes</td></tr>
    <tr><th scope="row">Check texture coverage (pink checkerboard warning)</th><td>Yes</td><td>Yes</td><td>Yes</td><td>No</td><td>No</td><td>No <sup>6</sup></td></tr>
    <tr><th scope="row">Extract UV map</th><td>Yes</td><td>Yes</td><td>Yes</td><td>No</td><td>No</td><td>No</td></tr>
    <tr class="matrix-section"><th colspan="7" scope="colgroup">Livery settings</th></tr>
    <tr><th scope="row">Details (title, ATC id and other fields)</th><td>Yes</td><td>Yes</td><td>Yes</td><td>No</td><td>No</td><td>Yes</td></tr>
    <tr><th scope="row">Registration number</th><td>Yes <sup>7</sup></td><td>Yes <sup>7</sup></td><td>Yes <sup>7</sup></td><td>No</td><td>No</td><td>Partly <sup>8</sup></td></tr>
    <tr><th scope="row">Availability (which configurations a livery appears under)</th><td>Not needed</td><td>Not needed</td><td>Yes</td><td>No</td><td>No</td><td>Partly <sup>9</sup></td></tr>
    <tr class="matrix-section"><th colspan="7" scope="colgroup">Previews and thumbnails</th></tr>
    <tr><th scope="row">3D preview, including click to add a texture</th><td>Yes</td><td>Yes</td><td>Yes</td><td>No</td><td>No</td><td>No</td></tr>
    <tr><th scope="row">Rendered thumbnails (experimental)</th><td>Yes</td><td>Yes</td><td>Yes</td><td>No</td><td>No</td><td>No</td></tr>
    <tr><th scope="row">Placeholder thumbnails, or your own images</th><td>Yes</td><td>Yes</td><td>Yes</td><td>No</td><td>No</td><td>Yes</td></tr>
    <tr class="matrix-section"><th colspan="7" scope="colgroup">Paintkit Builder</th></tr>
    <tr><th scope="row">Layered paintkit with albedo, composite and normal layers</th><td>Yes</td><td>Yes</td><td>Yes</td><td>No</td><td>No</td><td>Yes</td></tr>
    <tr><th scope="row">UV wireframe and paintable-area layers</th><td>Yes</td><td>Yes</td><td>Yes</td><td>No</td><td>No</td><td>No</td></tr>
    <tr><th scope="row">3D paintkit (experimental)</th><td>Yes</td><td>Yes</td><td>Yes</td><td>No</td><td>No</td><td>No</td></tr>
    <tr class="matrix-section"><th colspan="7" scope="colgroup">Compiling</th></tr>
    <tr><th scope="row">Compile with the MSFS SDK</th><td>Yes</td><td>Yes</td><td>Yes</td><td>No</td><td>No</td><td>Yes</td></tr>
    <tr><th scope="row">Compile without the SDK installed</th><td>Yes <sup>10</sup></td><td>No</td><td>No</td><td>No</td><td>No</td><td>No</td></tr>
  </tbody>
</table>

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
11. **Marked with a padlock** in the Discover aircraft list, so you can tell an encrypted aircraft from the others before you start.

<style>
  /* The theme gives every cell a 7.5rem minimum, which pushed this 7-column table past the content width. */
  .aircraft-matrix {
    font-size: 0.9em;
  }
  .aircraft-matrix th,
  .aircraft-matrix td {
    min-width: 0;
    padding: 0.35em 0.55em;
  }
  .aircraft-matrix td,
  .aircraft-matrix thead th {
    text-align: center;
  }
  .aircraft-matrix thead th[rowspan] {
    text-align: left;
    vertical-align: bottom;
  }
  .aircraft-matrix tbody th[scope="row"] {
    font-weight: normal;
    text-align: left;
    min-width: 11em;
  }
  .aircraft-matrix .matrix-groups th {
    font-size: 0.8em;
    letter-spacing: 0.06em;
    text-transform: uppercase;
  }
  /* A rule between the plain and encrypted halves, so the two groups of three read as groups. */
  .aircraft-matrix .matrix-encrypted-start,
  .aircraft-matrix tbody tr:not(.matrix-section) td:nth-of-type(4) {
    border-left: 2px solid rgba(255, 255, 255, 0.22);
  }
  .aircraft-matrix tr.matrix-section th {
    background: rgba(255, 255, 255, 0.07);
    border-top: 2px solid rgba(255, 255, 255, 0.22);
    font-size: 0.8em;
    font-weight: 700;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    text-align: left;
    padding-top: 0.8em;
  }
</style>

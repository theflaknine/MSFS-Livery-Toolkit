---
title: Paintkit Builder
nav_order: 4
---

# Paintkit Builder

Many aircraft never ship a paintkit. Without one you are painting blind: no idea where the panel lines
fall on the texture sheet, no idea which part of the image is the tail, and nothing underneath to trace.

The Paintkit Builder solves that by building a paintkit **from the aircraft itself**. It reads the
aircraft's own compiled textures and its 3D model's UV layout, and writes a layered Photoshop file you can
start painting on straight away.

It works on any aircraft you have installed, and it does **not** need a project. You can point it at an
aircraft you are only considering, look at what its textures are like, and decide from there.

You will find it in the sidebar, just above Settings.

---

## What you get

One `.psd` per texture, saved into a folder named after the aircraft, with these layers:

| Layer | What it is |
|:------|:-----------|
| **UV Wireframe** | The outline of the model's UV islands, so you can see exactly where each part of the aircraft lands on the image. |
| **Paintable Areas** | A black and white mask of those same islands, grown very slightly, for loading as a selection. |
| **Albedo** | The aircraft's existing paintwork, to paint over or trace. |
| **Ambient Occlusion** | Baked shading, taken from the aircraft's composite texture. |
| **Roughness** | How rough or glossy each part of the surface is. |
| **Metalness** | How metallic each part of the surface is. |
| **Normal** | The surface detail map. |

Only the **UV Wireframe** and **Albedo** are switched on when the file opens. The rest are included but
hidden, so they are there when you want to inspect or sample them without getting in your way.

Two details worth knowing:

- The **UV Wireframe** uses Difference blending, so it stays visible whether the paintwork underneath is
  light or dark. A plain white wireframe disappears over a white fuselage.
- **Paintable Areas** is a true black and white mask rather than a transparent layer, so you can load it as
  a selection (Ctrl-click the layer thumbnail in Photoshop) and paint without spilling outside the islands.
  It is grown by a few pixels on purpose, so paint can run slightly over an island edge without leaving a
  seam in the sim.

---

## Using it

**1. Choose an aircraft.** Click **Discover aircraft** and pick one from the list. Each entry shows where
it was found and whether it is an MSFS 2020 or MSFS 2024 aircraft, so you can tell two installs of the
same aircraft apart.

Stock and marketplace aircraft need the sim's Virtual File System running, exactly as elsewhere in the app.
See [Creating liveries]({{ '/creating-liveries.html' | relative_url }}) for how to start it.

**2. Choose what to build.** If the aircraft has several variants, pick the one you are painting first.
Then tick the textures you want a paintkit for, and tick which layers each file should contain. Your layer
choice is remembered for next time.

**3. Choose where to save it**, and click **Build paintkits**. A folder named after the aircraft is created
inside the location you pick, so building for several aircraft keeps them separate. You can set a default
location in [Settings]({{ '/configuration.html' | relative_url }}).

---

## Which textures should I paint?

Larger aircraft can list a lot of textures, and most of them are not what you are looking for. Two things
in the list help:

- **The copy count badge** (for example `x7`). This is how many places that texture appears across the
  aircraft, which usually means how many of the aircraft's own liveries repaint it. A texture that lots of
  liveries repaint is almost always one of the main painted surfaces, so the list is sorted by this to
  begin with. You can also sort by name or resolution.
- **The texture list under each name** tells you which maps that material actually has. A material with no
  composite texture simply cannot contribute Ambient Occlusion, Roughness or Metalness layers, and those
  layers will be left out of that particular file.

---

## Starting from an existing paint scheme

If the aircraft ships more than one livery, a **Use textures from** box appears. Leave it on **Aircraft
default** to build from the aircraft's own base paintwork, or pick one of its liveries to build from that
scheme instead.

Anything the livery you pick does not repaint is taken from the aircraft's own textures, which is exactly
how the simulator itself resolves a livery. Only liveries that belong to the variant you selected are
offered, so you will not be shown a scheme that does not fit.

---

## Notes

- Paintkits can be large. A full set of layers at 4K is typically well under 100 MB, but an 8K texture with
  every layer switched on can reach around half a gigabyte. Turning off layers you do not need keeps the
  files much smaller.
- For very large textures (above 8K) a **half resolution** option appears. Photoshop files have a hard 2 GB
  size limit, and this keeps you comfortably under it. You will rarely see this option.
- The generated files are ordinary layered `.psd` files. They are designed and tested against Adobe
  Photoshop.
- Building a lot of textures at once takes a while. The app stays locked while it works, and there is a
  **Cancel** button if you change your mind.

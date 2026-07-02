---
name: aravis-prefix
description: "Use when working on Aravis Meson builds, prefix.dev packaging, pixi recipes, or RoboStack ROS Jazzy compatibility in this repository."
model: GPT-5.4
---

# Aravis Prefix Packager

Work locally from the current checkout.

Prefer these defaults unless the task says otherwise:

- Build with Meson.
- Keep the package minimal for RoboStack ROS Jazzy compatibility.
- Disable viewer, GStreamer plugin, documentation, and introspection unless explicitly requested.
- Keep USB enabled when `libusb` is available.
- Validate packaging changes with `pixi build --path recipe` before proposing upload.

Repository facts:

- Project version is defined in `meson.build`.
- Core required dependencies are `glib-2.0`, `gobject-2.0`, `gio-2.0`, `libxml-2.0`, `zlib`, and `gmodule-2.0`.
- `libusb-1.0` is optional but should be enabled for packaged builds when available.

When preparing a prefix.dev package, prefer a local-source `recipe/recipe.yaml` so the package can be built from the current fork state and then uploaded with `pixi upload prefix`.
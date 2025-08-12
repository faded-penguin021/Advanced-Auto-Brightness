---
layout: default
---

# User Guide

## Welcome to Advanced Auto Brightness
This project replaces the built‑in auto brightness with a smoother, more intelligent, and fully customizable system that adapts to light the way you want it to.

## 1. Getting Started: Two‑Step Activation
1. **Activate the Service**: In the **General** tab, flip the master switch (top right). A persistent notification confirms AAB is active. This also disables Android’s native auto brightness.
2. **Set Your Boundaries**: In the **Misc** tab, adjust **Min Brightness** and **Max Brightness**. These define the absolute darkest and brightest your screen will get.

> Tip: On OLED phones, setting Min Brightness to 5–10 (instead of 0) can prevent “black crush” (loss of detail in dark areas).

## 2. Understanding the Control Panel
- **General**: Defines the shape of your brightness curve — “what brightness for this ambient light?”
- **Reactivity**: Controls sensor behavior — “when should I react and how sensitive should I be?”
- **Misc**: Global rules and feel — brightness limits, animation controls, and fine‑tuning.

## 3. Tuning Your Brightness Curve (General)
The curve uses a three‑part design for precise control:
- **Zone 1 (Dark → Dim)**
  - `Zone 1 Scaling`: Main control for low light. Increase to brighten faster in the dark.
  - `Zone 1 End`: Lux level where “dark” ends and “dim” begins.
- **Zone 2 (Dim → Medium)**
  - `Zone 2 Scaling` & `Offset`: Shape the curve for common indoor levels. Use the graph to preview.
- **Zone 3 (Bright)**
  - Handled automatically to smoothly approach max brightness, avoiding harsh jumps outdoors.

## 4. Eliminating Flicker (Reactivity)
Minor sensor noise can cause jitter. Use a dead‑zone so the screen reacts only to significant changes.
- **Thresholds**: `Dark`, `Dim`, and `Bright Threshold` set dead‑zone size (as %). Higher = more stable, less reactive.
- **Curve**: `Curve Mid` and `Slope` make the dead‑zone transition smoothly across lux levels.

> Long‑press any setting label in any tab to see a detailed tooltip.

## 5. Visualize Before You Apply
- **Brightness Graph (General)**: Teal = your curve; Yellow = reference. Adjust until the teal line matches your preference.
- **Reactivity Graph (Reactivity)**: Visualizes your dead‑zone curve and stability across lux levels.

## 6. Saving Your Work
- **Save & Apply**: Persist changes and apply immediately.
- **Reset tab defaults**: Revert the current tab to original values.
- **Exit**: Close the control panel without saving.

Enjoy your new intelligent auto brightness!

## Media
- Demo (human‑made): `assets/demo.mp4` — Real‑world example showing smooth, flicker‑free adaptation.
- High‑level overview (AI‑generated): `assets/aab-demo.mp4` — Project goals, core features, and tuning workflow.
- Attribution: The overview video was created by NotebookLM via AI.

[![Deploy Pages](https://github.com/faded-penguin021/Advanced-Auto-Brightness/actions/workflows/pages.yml/badge.svg)](https://github.com/faded-penguin021/Advanced-Auto-Brightness/actions/workflows/pages.yml) [![Release](https://github.com/faded-penguin021/Advanced-Auto-Brightness/actions/workflows/release.yml/badge.svg)](https://github.com/faded-penguin021/Advanced-Auto-Brightness/actions/workflows/release.yml)


**Author**: [/u/v_uurtjevragen](https://www.reddit.com/user/v_uurtjevragen)  
**Project version**: 3.0


# Advanced Auto Brightness 3.0
# Advanced Auto Brightness 3.0

A Tasker project that dynamically adjusts your Android screen brightness based on ambient light and device state for smarter, smoother lighting.

## Features
- Proximity-aware dimming
- Ambient sensor monitoring with accuracy gating
- Adjustable thresholds for day/night
- Optional trust of unreliable sensor readings
- Battery-friendly cadence

## Quick Start
1. Install Tasker (`https://play.google.com/store/apps/details?id=net.dinglisch.android.taskerm`).
2. Download the latest release from the Releases page.
3. In Tasker, long-press the bottom bar, tap Import, and choose the `.prj.xml` file.
4. Configure variables (thresholds, trust options) inside Tasker as needed.

## Download
- Grab the latest `.prj.xml` from the [Releases](`https://github.com/faded-penguin021/Advanced-Auto-Brightness/releases`) page.

## Screenshots

https://github.com/faded-penguin021/Advanced-Auto-Brightness/raw/main/assets/demo.gif


Demo: https://imgur.com/a/advanced-auto-brightness-3-0-demo-VxGcnYH

Place screenshots or a demo GIF in `assets/` and reference them here.

## How it works

## Configure in-app (recommended)
Use the built-in scenes to configure everything: General, Reactivity, Brightness, Misc, and About. Manual variable editing is only for advanced tweaking.

Sensor events are filtered for accuracy, compared to thresholds, then brightness is adjusted smoothly to avoid flicker.

## Contributing / Updating
- Replace `tasker/Advanced-Auto-Brightness.prj.xml` with your updated export
- Bump a tag `vX.Y.Z` to publish a release (workflow attaches the project file)

## License
MIT. See `LICENSE`.


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

- Sensor pipeline: Subscribes to ambient light updates, applies accuracy gating (with an option to trust unreliable readings), and throttles sampling to save battery.
- Proximity-aware: Uses proximity detection to dampen or block updates when the sensor is covered (e.g., pocket/face). Initializes cleanly on display-on and hibernates on display-off.
- Curve mapping: A configurable brightness curve maps lux → target brightness; tune it in the Brightness tab with a live graph.
- Dynamic dead‑zone: A log-scale dead‑zone ignores minor lux jitter to eliminate flicker; visualize/tune it in the Reactivity graph.
- Adaptive smoothing (dynamic alpha): Small changes are smoothed slowly; large, intentional deltas ramp quickly but remain smooth; explore it in the Alpha graph.
- Animation and limits: Tapering and caps prevent jarring jumps and respect min/max limits for comfort.
- Overrides and controls: A manual override switch, persistent notification, and paused/foreground states give you full control at a glance.
## Contributing / Updating
- Replace `tasker/Advanced-Auto-Brightness.prj.xml` with your updated export
- Bump a tag `vX.Y.Z` to publish a release (workflow attaches the project file)

## License
MIT. See `LICENSE`.


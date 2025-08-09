[![Deploy Pages](https://github.com/faded-penguin021/Advanced-Auto-Brightness/actions/workflows/pages.yml/badge.svg)](https://github.com/faded-penguin021/Advanced-Auto-Brightness/actions/workflows/pages.yml) [![Release](https://github.com/faded-penguin021/Advanced-Auto-Brightness/actions/workflows/release.yml/badge.svg)](https://github.com/faded-penguin021/Advanced-Auto-Brightness/actions/workflows/release.yml) [![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE) [![Latest release](https://img.shields.io/github/v/release/faded-penguin021/Advanced-Auto-Brightness)](https://github.com/faded-penguin021/Advanced-Auto-Brightness/releases) [![GitHub stars](https://img.shields.io/github/stars/faded-penguin021/Advanced-Auto-Brightness?style=social)](https://github.com/faded-penguin021/Advanced-Auto-Brightness/stargazers)


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

## Technical details

Notation: raw lux L(t), smoothed lux S(t), target brightness T(t), applied brightness B(t).

- Sensor cadence and gating:
  - Listens to the ambient sensor and applies accuracy gating (uses Tasker %as_accuracy); unreliable readings can be ignored unless explicitly trusted.
  - Sampling cadence is configurable and throttled to conserve battery.

- Log-domain dead‑zone (anti‑flicker):
  - Work in log‑lux to align with human perception: x = log10(L).
  - If |x − x_prev| < DZ(x) then treat as noise and suppress/slow the update.
  - DZ(x) is user‑tunable via the Reactivity tab and visualized in the Reactivity graph.

- Adaptive smoothing (dynamic alpha):
  - Exponential smoothing on lux with an adaptive coefficient α that grows with the magnitude of change:
    \[ S_t = (1 - lpha_t)\,S_{t-1} + lpha_t\,L_t \]
  - A typical form: 
    \[ lpha_t = \mathrm{clamp}(lpha_{min} + k\,g(|L_t - S_{t-1}|),\ lpha_{min},\ lpha_{max}) \]
    where k is the Delta factor (see %AAB_DeltaFactor) and g is a monotonic function (e.g., log1p). Small deltas => slow, big deltas => fast.
  - Explore behavior in the Alpha graph.

- Curve mapping (lux → target brightness):
  - Compute log‑lux z = log10(S_t). Map z through a user‑tunable curve to produce T_t in [0,1].
  - Curve steepness (see %AAB_ScaleSteepness) controls how aggressively mid‑range lux affects brightness. Tune in the Brightness tab with the live graph.

- Tapering and limits:
  - Rate‑limit changes to avoid jarring steps and respect min/max caps: 
    \[ B_t = \mathrm{clamp}(\mathrm{taper}(B_{t-1}, T_t, r_{up}, r_{down}),\ B_{min},\ B_{max}) \]

- Proximity/state handling:
  - Proximity detection dampens or suspends updates when the sensor is covered (e.g., pocket/ear).
  - Initialize cleanly on display‑on; hibernate and remove timers on display‑off.

- Overrides and controls:
  - Manual override switch, persistent notification, and paused/foreground modes provide explicit control when needed.

Parameters you can tune in‑app:
- Reactivity (dead‑zone size/shape, dynamic alpha behavior)
- Brightness curve (steepness and overall shape)
- Limits and taper rates
- Sensor accuracy policy and cadence

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


## Requirements
- Tasker 6.6+ recommended (built/tested on 6.6.x)
- Android 10+ recommended (works on many versions)
- Permissions: Modify System Settings; Notification access (for controls)

## Troubleshooting
- Brightness not changing: grant Modify System Settings in Android Settings → Apps → Tasker → Special access.
- No sensor updates: disable battery optimizations for Tasker.
- Flicker: increase the Reactivity dead‑zone or smoothing.
- Too slow/fast: adjust Delta factor (dynamic alpha) and taper rates.
- Stuck brightness: check that Manual Override is off in the control panel.

## FAQ
- Does this replace Android auto-brightness? Yes—turn off the system feature for best results.
- Can I keep system auto-brightness on? Not recommended; they will fight each other.
- Can I tune per-app? Use Tasker profiles/contexts as you like; AAB exposes controls and states you can combine.
- How do I revert? Toggle the master switch or remove the project from Tasker.


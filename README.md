[![Deploy Pages](https://github.com/faded-penguin021/Advanced-Auto-Brightness/actions/workflows/pages.yml/badge.svg)](https://github.com/faded-penguin021/Advanced-Auto-Brightness/actions/workflows/pages.yml) [![Release](https://github.com/faded-penguin021/Advanced-Auto-Brightness/actions/workflows/release.yml/badge.svg)](https://github.com/faded-penguin021/Advanced-Auto-Brightness/actions/workflows/release.yml) [![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE) [![Latest release](https://img.shields.io/github/v/release/faded-penguin021/Advanced-Auto-Brightness)](https://github.com/faded-penguin021/Advanced-Auto-Brightness/releases) [![Downloads](https://img.shields.io/github/downloads/faded-penguin021/Advanced-Auto-Brightness/total.svg)](https://github.com/faded-penguin021/Advanced-Auto-Brightness/releases)
[![Deploy Pages](https://github.com/faded-penguin021/Advanced-Auto-Brightness/actions/workflows/pages.yml/badge.svg)](https://github.com/faded-penguin021/Advanced-Auto-Brightness/actions/workflows/pages.yml) [![Release](https://github.com/faded-penguin021/Advanced-Auto-Brightness/actions/workflows/release.yml/badge.svg)](https://github.com/faded-penguin021/Advanced-Auto-Brightness/actions/workflows/release.yml) [![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE) [![Latest release](https://img.shields.io/github/v/release/faded-penguin021/Advanced-Auto-Brightness)](https://github.com/faded-penguin021/Advanced-Auto-Brightness/releases) [![Downloads](https://img.shields.io/github/downloads/faded-penguin021/Advanced-Auto-Brightness/total.svg)](https://github.com/faded-penguin021/Advanced-Auto-Brightness/releases)


**Author**: [/u/v_uurtjevragen](https://www.reddit.com/user/v_uurtjevragen)
**Author**: [/u/v_uurtjevragen](https://www.reddit.com/user/v_uurtjevragen)
**Project version**: 3.0
**Project version**: 3.0


# Advanced Auto Brightness 3.0
# Advanced Auto Brightness 3.0


A Tasker project that dynamically adjusts Android screen brightness based on ambient light and device state for smoother, smarter lighting.
A Tasker project that dynamically adjusts Android screen brightness based on ambient light and device state for smoother, smarter lighting.


> Important: Requires Tasker 6.6.2‑beta or newer. On older Tasker, import will fail with “Unknown Action: Get Sunrise/Sunset.” See Requirements for beta opt‑in.
> Important: Requires Tasker 6.6.2‑beta or newer. On older Tasker, import will fail with “Unknown Action: Get Sunrise/Sunset.” See Requirements for beta opt‑in.


## Features
## Features
- Proximity-aware dimming
- Proximity-aware dimming
- Sensor accuracy gating
- Sensor accuracy gating
- Adjustable lux→brightness curve (live graph)
- Adjustable lux→brightness curve (live graph)
- Dynamic dead‑zone to eliminate flicker
- Dynamic dead‑zone to eliminate flicker
- Adaptive smoothing (dynamic alpha) with tapered animations
- Adaptive smoothing (dynamic alpha) with tapered animations
- Foreground controls and battery-friendly cadence
- Foreground controls and battery-friendly cadence


## Quick Start
## Quick Start
Helpful links: [User Guide](docs/user-guide.md) · [Discussions](https://github.com/faded-penguin021/Advanced-Auto-Brightness/discussions) · [Releases](https://github.com/faded-penguin021/Advanced-Auto-Brightness/releases)
Helpful links: [User Guide](docs/user-guide.md) · [Discussions](https://github.com/faded-penguin021/Advanced-Auto-Brightness/discussions) · [Releases](https://github.com/faded-penguin021/Advanced-Auto-Brightness/releases)


1. Install Tasker (`https://play.google.com/store/apps/details?id=net.dinglisch.android.taskerm`).
1. Install Tasker (`https://play.google.com/store/apps/details?id=net.dinglisch.android.taskerm`).
2. Download the latest release from the Releases page.
2. Download the latest release from the Releases page.
3. In Tasker: long‑press the home icon (bottom left) → Import Project.`.prj.xml`.
3. In Tasker: long‑press the home icon (bottom left) → Import Project.`.prj.xml`.
4. Configure via the in‑app scenes (General, Reactivity, Brightness, Misc).
4. Configure via the in‑app scenes (General, Reactivity, Brightness, Misc).


## Download
## Download
- Latest `.prj.xml`: see [Releases](https://github.com/faded-penguin021/Advanced-Auto-Brightness/releases)
- Latest `.prj.xml`: see [Releases](https://github.com/faded-penguin021/Advanced-Auto-Brightness/releases)


### Scan to download
### Scan to download
![Scan to download](https://api.qrserver.com/v1/create-qr-code/?size=240x240&data=https%3A%2F%2Fgithub.com%2Ffaded-penguin021%2FAdvanced-Auto-Brightness%2Freleases%2Flatest%2Fdownload%2FAdvanced-Auto-Brightness.prj.xml)
![Scan to download](https://api.qrserver.com/v1/create-qr-code/?size=240x240&data=https%3A%2F%2Fgithub.com%2Ffaded-penguin021%2FAdvanced-Auto-Brightness%2Freleases%2Flatest%2Fdownload%2FAdvanced-Auto-Brightness.prj.xml)


## Demo
## Demo
<video controls loop muted playsinline width="720">
<video controls loop muted playsinline width="720">
  <source src="https://i.imgur.com/LaTv3iX.mp4" type="video/mp4">
  <source src="https://i.imgur.com/LaTv3iX.mp4" type="video/mp4">
  <source src="https://github.com/faded-penguin021/Advanced-Auto-Brightness/raw/main/assets/demo.mp4" type="video/mp4">
  <source src="https://github.com/faded-penguin021/Advanced-Auto-Brightness/raw/main/assets/demo.mp4" type="video/mp4">
  Your browser does not support the video tag.
  Your browser does not support the video tag.
</video>
</video>


## How it works
## How it works
- Sensor pipeline: accuracy gating (optionally trust unreliable), throttled sampling.
- Sensor pipeline: accuracy gating (optionally trust unreliable), throttled sampling.
- Proximity-aware: dampens/blocks when covered; clean init on display‑on, hibernate on display‑off.
- Proximity-aware: dampens/blocks when covered; clean init on display‑on, hibernate on display‑off.
- Curve mapping: configurable lux→target brightness with live preview.
- Curve mapping: configurable lux→target brightness with live preview.
- Dynamic dead‑zone: log‑scale jitter suppression.
- Dynamic dead‑zone: log‑scale jitter suppression.
- Adaptive smoothing: dynamic alpha; small deltas slow, big deltas fast; tapered animations.
- Adaptive smoothing: dynamic alpha; small deltas slow, big deltas fast; tapered animations.
- Controls: manual override, persistent notification, paused/foreground states.
- Controls: manual override, persistent notification, paused/foreground states.


## Technical details
## Technical details
Notation: raw lux L(t), smoothed lux S(t), target brightness T(t), applied brightness B(t).
Notation: raw lux L(t), smoothed lux S(t), target brightness T(t), applied brightness B(t).


- Sensor cadence and gating
- Sensor cadence and gating
  - Uses `%as_accuracy`; unreliable readings ignored unless trusted.
  - Uses `%as_accuracy`; unreliable readings ignored unless trusted.
  - Sampling cadence is configurable and battery‑friendly.
  - Sampling cadence is configurable and battery‑friendly.


- Dead‑zone (log domain)
- Dead‑zone (log domain)
  - x = log10(L). If |x − x_prev| < DZ(x) then treat as noise.
  - x = log10(L). If |x − x_prev| < DZ(x) then treat as noise.


- Adaptive smoothing
- Adaptive smoothing
```
```
S_t = (1 - alpha_t) * S_{t-1} + alpha_t * L_t
S_t = (1 - alpha_t) * S_{t-1} + alpha_t * L_t
alpha_t = clamp(alpha_min + k * g(|L_t - S_{t-1}|), alpha_min, alpha_max)
alpha_t = clamp(alpha_min + k * g(|L_t - S_{t-1}|), alpha_min, alpha_max)
```
```
  - k is the Delta factor; g is monotonic (e.g., log1p).
  - k is the Delta factor; g is monotonic (e.g., log1p).


- Curve and limits
- Curve and limits
```
```
B_t = clamp(taper(B_{t-1}, T_t, r_up, r_down), B_min, B_max)
B_t = clamp(taper(B_{t-1}, T_t, r_up, r_down), B_min, B_max)
```
```


## Contributing / Updating
## Contributing / Updating
- Replace `tasker/Advanced-Auto-Brightness.prj.xml` with your export.
- Replace `tasker/Advanced-Auto-Brightness.prj.xml` with your export.
- Add screenshots/video under `assets/`.
- Add screenshots/video under `assets/`.
- Tag a version like `v3.0.1` to publish a release (artifacts upload automatically).
- Tag a version like `v3.0.1` to publish a release (artifacts upload automatically).


## License
## License
MIT. See `LICENSE`.
MIT. See `LICENSE`.


## Requirements
- Direct beta info: Reddit: https://www.reddit.com/r/tasker/comments/1lulpiq/dev_tasker_662beta_shizuku_integration/
## Requirements
- Tasker 6.6.2‑beta+ for circadian (Sunrise/Sunset) actions
- Tasker 6.6.2‑beta+ for circadian (Sunrise/Sunset) actions
- Join beta via the [Play Store page](https://play.google.com/store/apps/details?id=net.dinglisch.android.taskerm) → “Join the beta”
- Join beta via the [Play Store page](https://play.google.com/store/apps/details?id=net.dinglisch.android.taskerm) → “Join the beta”
- Without beta: project imports, but circadian engine won’t be available
- Without beta: project imports, but circadian engine won’t be available
- Tasker 6.6+ recommended; Android 10+ recommended
- Tasker 6.6+ recommended; Android 10+ recommended
- Permissions: Modify System Settings; Notification access
- Permissions: Modify System Settings; Notification access


## Troubleshooting
## Troubleshooting
- Import fails: update to Tasker 6.6.2‑beta (Unknown Action: Get Sunrise/Sunset)
- Import fails: update to Tasker 6.6.2‑beta (Unknown Action: Get Sunrise/Sunset)
- Brightness not changing: grant Modify System Settings (Android Settings → Apps → Tasker → Special access)
- Brightness not changing: grant Modify System Settings (Android Settings → Apps → Tasker → Special access)
- No sensor updates: disable battery optimizations for Tasker
- No sensor updates: disable battery optimizations for Tasker
- Flicker: increase Reactivity dead‑zone or smoothing
- Flicker: increase Reactivity dead‑zone or smoothing
- Too slow/fast: adjust Delta factor (dynamic alpha). Note: taper rates affect dynamic scale compression, not raw responsiveness.
- Too slow/fast: adjust Delta factor (dynamic alpha). Note: taper rates affect dynamic scale compression, not raw responsiveness.


## FAQ
## FAQ
- Replace Android auto‑brightness? Yes—turn off the system feature
- Replace Android auto‑brightness? Yes—turn off the system feature
- Keep system auto‑brightness on? Not recommended; they will fight
- Keep system auto‑brightness on? Not recommended; they will fight
- Per‑app tuning? Use Tasker profiles/contexts with AAB controls
- Per‑app tuning? Use Tasker profiles/contexts with AAB controls


## Privacy
## Privacy
- No analytics or network; all processing on‑device
- No analytics or network; all processing on‑device


## Known limitations
## Known limitations
- OEM/Android min/max clamps vary by device
- OEM/Android min/max clamps vary by device
- Sensor cadence/accuracy varies; tune Reactivity/Alpha accordingly
- Sensor cadence/accuracy varies; tune Reactivity/Alpha accordingly

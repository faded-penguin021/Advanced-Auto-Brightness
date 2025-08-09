---
layout: default
---

# Advanced Auto Brightness 3.0

Links: [User Guide](./user-guide.html) · [Releases](https://github.com/faded-penguin021/Advanced-Auto-Brightness/releases) · [Discussions](https://github.com/faded-penguin021/Advanced-Auto-Brightness/discussions)

Author: [/u/v_uurtjevragen](https://www.reddit.com/user/v_uurtjevragen)
Version: 3.0

Smart, proximity‑aware automatic brightness for Android via Tasker.

- Website: https://faded-penguin021.github.io/Advanced-Auto-Brightness/
- Repo: https://github.com/faded-penguin021/Advanced-Auto-Brightness
- Download latest: https://github.com/faded-penguin021/Advanced-Auto-Brightness/releases/latest/download/Advanced-Auto-Brightness.prj.xml

> Important: Requires Tasker 6.6.2‑beta or newer. On older Tasker, import will fail with “Unknown Action: Get Sunrise/Sunset.”

## Quick Start
1. Install Tasker from Google Play.
2. Download the `.prj.xml` above.
3. In Tasker, long‑press the home icon (bottom left) → Import Project.

## Features
- Proximity‑aware dimming
- Sensor accuracy gating
- Adjustable thresholds
- Smooth adjustments to reduce flicker

## Demo
<video controls loop muted playsinline width="720" src="https://i.imgur.com/LaTv3iX.mp4"></video>

## How it works
- Sensor pipeline: accuracy gating (optionally trust unreliable), throttled sampling.
- Proximity‑aware: dampens/blocks when covered; clean init on display‑on, hibernate on display‑off.
- Curve mapping: configurable lux→target brightness with live graph.
- Dynamic dead‑zone: log‑scale jitter suppression.
- Adaptive smoothing (dynamic alpha): fast for big deltas, slow for small; tapered animations.
- Controls: manual override, persistent notification, paused/foreground states.

## Technical details
Notation: raw lux L(t), smoothed lux S(t), target brightness T(t), applied brightness B(t).

- Sensor cadence and gating
  - Uses `%as_accuracy`; unreliable readings ignored unless trusted.
  - Sampling cadence is configurable and battery‑friendly.

- Dead‑zone (log domain)
  - x = log10(L). If |x − x_prev| < DZ(x) then treat as noise.

- Adaptive smoothing
```
S_t = (1 - alpha_t) * S_{t-1} + alpha_t * L_t
alpha_t = clamp(alpha_min + k * g(|L_t - S_{t-1}|), alpha_min, alpha_max)
```

- Curve and limits
```
B_t = clamp(taper(B_{t-1}, T_t, r_up, r_down), B_min, B_max)
```

## Download
- Latest `.prj.xml`: link above

### Scan to download
![Scan to download](https://api.qrserver.com/v1/create-qr-code/?size=240x240&data=https%3A%2F%2Fgithub.com%2Ffaded-penguin021%2FAdvanced-Auto-Brightness%2Freleases%2Flatest%2Fdownload%2FAdvanced-Auto-Brightness.prj.xml)

## Requirements
- Tasker 6.6.2‑beta+ for circadian (Sunrise/Sunset) actions
- Join the beta via the Play Store page (scroll to “Join the beta”)
- Reddit info: https://www.reddit.com/r/tasker/comments/1lulpiq/dev_tasker_662beta_shizuku_integration/
- Without the beta, the project will import, but the circadian engine won’t be available.

## Troubleshooting
- Brightness not changing: grant Modify System Settings
- No sensor updates: disable battery optimizations for Tasker
- Flicker: increase the Reactivity dead‑zone or smoothing
- Too slow/fast: adjust Delta factor (dynamic alpha). Note: taper rates affect dynamic scale compression, not raw responsiveness.

## FAQ
- Does this replace Android auto‑brightness? Yes—turn off the system feature for best results.
- Can I keep system auto‑brightness on? Not recommended; they will fight each other.

## Privacy
- No analytics; all processing on‑device

## Known limitations
- Brightness control APIs differ across OEMs/Android versions; some devices may clamp min/max.
- Sensor accuracy and cadence vary by device; tune Reactivity and Alpha accordingly.

## Updating
Replace `tasker/Advanced-Auto-Brightness.prj.xml` in the repo and push a tag like `v3.0.1` to publish a new release.

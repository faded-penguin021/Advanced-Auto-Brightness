---
layout: default
---

# Advanced Auto Brightness 3.0

Links: [User Guide](./user-guide.html) · [Releases](https://github.com/faded-penguin021/Advanced-Auto-Brightness/releases) · [Discussions](https://github.com/faded-penguin021/Advanced-Auto-Brightness/discussions)

Author: [/u/v_uurtjevragen](https://www.reddit.com/user/v_uurtjevragen)
Version: 3.0

Smart, proximity-aware automatic brightness for Android via Tasker.

- Website: https://faded-penguin021.github.io/Advanced-Auto-Brightness/
- Repo: https://github.com/faded-penguin021/Advanced-Auto-Brightness
- Download latest: https://github.com/faded-penguin021/Advanced-Auto-Brightness/releases/latest/download/Advanced-Auto-Brightness.prj.xml

## Quick Start
1. Install Tasker from Google Play.
2. Download the `.prj.xml` above.
3. In Tasker, long-press the bottom bar → Import → select the file.

## Features
- Proximity-aware dimming
- Sensor accuracy gating
- Adjustable thresholds
- Smooth adjustments to reduce flicker

## Demo
<video controls loop muted playsinline width="720" src="https://github.com/faded-penguin021/Advanced-Auto-Brightness/raw/main/assets/demo.mp4"></video>

## How it works
- Sensor pipeline: subscribes to ambient light updates, applies accuracy gating (option to trust unreliable), and throttles sampling to save battery.
- Proximity-aware: dampens or blocks updates when covered (e.g., pocket/face). Clean init on display‑on; hibernate on display‑off.
- Curve mapping: a configurable curve maps lux → target brightness; tune it in the Brightness tab with a live graph.
- Dynamic dead‑zone: a log-scale dead‑zone ignores minor lux jitter to eliminate flicker; visualize/tune in the Reactivity graph.
- Adaptive smoothing (dynamic alpha): small changes are smoothed slowly; large, intentional deltas ramp quickly but remain smooth; explore in the Alpha graph.
- Animation and limits: tapering and caps prevent jarring jumps and respect min/max limits.
- Overrides and controls: manual override switch, persistent notification, and paused/foreground states give you full control at a glance.

## Technical details
Notation: raw lux L(t), smoothed lux S(t), target brightness T(t), applied brightness B(t).

- Sensor cadence and gating:
  - Uses Tasker `%as_accuracy`; unreliable readings ignored unless explicitly trusted.
  - Sampling cadence is configurable and throttled to conserve battery.

- Log-domain dead‑zone (anti‑flicker):
  - Work in log‑lux to align with perception: x = log10(L).
  - If |x − x_prev| < DZ(x) treat as noise and suppress/slow the update.
  - DZ(x) is user‑tunable in the Reactivity tab and visualized in the Reactivity graph.

- Adaptive smoothing (dynamic alpha):
```
S_t = (1 - alpha_t) * S_{t-1} + alpha_t * L_t
alpha_t = clamp(alpha_min + k * g(|L_t - S_{t-1}|), alpha_min, alpha_max)
```

- Curve mapping (lux → target brightness):
  - Compute z = log10(S_t). Map z through a user‑tunable curve to produce T_t in [0,1].
  - Curve steepness controls mid‑range sensitivity.

- Tapering and limits:
```
B_t = clamp(taper(B_{t-1}, T_t, r_up, r_down), B_min, B_max)
```

## Download
- Latest `.prj.xml`: link above

### Scan to download
![Scan to download](https://api.qrserver.com/v1/create-qr-code/?size=240x240&data=https%3A%2F%2Fgithub.com%2Ffaded-penguin021%2FAdvanced-Auto-Brightness%2Freleases%2Flatest%2Fdownload%2FAdvanced-Auto-Brightness.prj.xml)

## Requirements
- Tasker 6.6+ recommended (built/tested on 6.6.x)
- Android 10+ recommended (works on many versions)
- Permissions: Modify System Settings; Notification access (for controls)

## Troubleshooting
- Brightness not changing: grant Modify System Settings in Android Settings → Apps → Tasker → Special access.
- No sensor updates: disable battery optimizations for Tasker.
- Flicker: increase the Reactivity dead‑zone or smoothing.
- Too slow/fast: adjust Delta factor (dynamic alpha) and taper rates.

## FAQ
- Does this replace Android auto-brightness? Yes—turn off the system feature for best results.
- Can I keep system auto-brightness on? Not recommended; they will fight each other.

## Privacy
- No analytics, accounts, or network connectivity required.
- All processing happens on-device in Tasker; nothing is uploaded.

## Known limitations
- Brightness control APIs differ across OEMs/Android versions; some devices may clamp min/max.
- Sensor accuracy and cadence vary by device; tune Reactivity and Alpha accordingly.

## Updating
Replace `tasker/Advanced-Auto-Brightness.prj.xml` in the repo and push a tag like `v3.0.1` to publish a new release.

---
---
layout: default
layout: default
---
---


# Advanced Auto Brightness 3.0
# Advanced Auto Brightness 3.0


Author: [/u/v_uurtjevragen](https://www.reddit.com/user/v_uurtjevragen)
Author: [/u/v_uurtjevragen](https://www.reddit.com/user/v_uurtjevragen)
Version: 3.0
Version: 3.0




Smart, proximity-aware automatic brightness for Android via Tasker.
Smart, proximity-aware automatic brightness for Android via Tasker.


- Website: https://faded-penguin021.github.io/Advanced-Auto-Brightness/
- Website: https://faded-penguin021.github.io/Advanced-Auto-Brightness/
- Repo: https://github.com/faded-penguin021/Advanced-Auto-Brightness
- Repo: https://github.com/faded-penguin021/Advanced-Auto-Brightness
- Download latest: https://github.com/faded-penguin021/Advanced-Auto-Brightness/releases/latest/download/Advanced-Auto-Brightness.prj.xml
- Download latest: https://github.com/faded-penguin021/Advanced-Auto-Brightness/releases/latest/download/Advanced-Auto-Brightness.prj.xml


## Quick Start
## Quick Start
1. Install Tasker from Google Play.
1. Install Tasker from Google Play.
2. Download the `.prj.xml` above.
2. Download the `.prj.xml` above.
3. In Tasker, long-press the bottom bar → Import → select the file.
3. In Tasker, long-press the bottom bar → Import → select the file.


## Features
## Features


## How it works
- Sensor pipeline: Subscribes to ambient light updates, applies accuracy gating (with an option to trust unreliable readings), and throttles sampling to save battery.
- Proximity-aware: Uses proximity detection to dampen or block updates when the sensor is covered (e.g., pocket/face). Initializes cleanly on display-on and hibernates on display-off.
- Curve mapping: A configurable brightness curve maps lux → target brightness; tune it in the Brightness tab with a live graph.
- Dynamic dead‑zone: A log-scale dead‑zone ignores minor lux jitter to eliminate flicker; visualize/tune it in the Reactivity graph.
- Adaptive smoothing (dynamic alpha): Small changes are smoothed slowly; large, intentional deltas ramp quickly but remain smooth; explore it in the Alpha graph.
- Animation and limits: Tapering and caps prevent jarring jumps and respect min/max limits for comfort.
- Overrides and controls: A manual override switch, persistent notification, and paused/foreground states give you full control at a glance.


<video controls loop muted playsinline width=640 src="https://github.com/faded-penguin021/Advanced-Auto-Brightness/raw/main/assets/demo.mp4"></video>
<video controls loop muted playsinline width=640 src="https://github.com/faded-penguin021/Advanced-Auto-Brightness/raw/main/assets/demo.mp4"></video>




Demo: https://imgur.com/a/advanced-auto-brightness-3-0-demo-VxGcnYH
Demo: https://imgur.com/a/advanced-auto-brightness-3-0-demo-VxGcnYH


- Proximity-aware dimming
- Proximity-aware dimming
- Sensor accuracy gating
- Sensor accuracy gating
- Adjustable thresholds
- Adjustable thresholds
- Smooth adjustments to reduce flicker
- Smooth adjustments to reduce flicker


## Updating
## Updating
Replace `tasker/Advanced-Auto-Brightness.prj.xml` in the repo and push a tag like `v0.1.1` to publish a new release.
Replace `tasker/Advanced-Auto-Brightness.prj.xml` in the repo and push a tag like `v0.1.1` to publish a new release.

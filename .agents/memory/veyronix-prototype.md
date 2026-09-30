---
name: VEYRONIX prototype constraints
description: Durable product decisions for the VEYRONIX SIH 2026 prototype.
---

The VEYRONIX SIH prototype should remain usable without external hardware, paid APIs, GPS permissions, or hosted AI services. Treat local simulation and localStorage as first-class demo behavior rather than temporary placeholders.

**Why:** The final demo needs to run reliably in an evaluation environment and show the end-to-end waste handoff even when no sensors, camera, GPS device, or network integration is available.

**How to apply:** Preserve centralized shared state, Asia/Kolkata timestamps derived from the browser clock, and explicit simulated controls for AI confidence, trolley movement, GPS failure/recovery, offline mode, alerts, and audit activity.
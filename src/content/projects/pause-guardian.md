---
title: 'Pause Guardian'
description: 'A Garmin Connect IQ diagnostic exploring whether a watch can detect when an athlete forgets to resume a paused activity.'
pubDate: 'Aug 10 2026'
stack: ['Monkey C', 'Garmin Connect IQ', 'GPS', 'FitContributor']
github: 'https://github.com/PawanPatil19/pause-guardian'
featured: true
---

Pause Guardian investigates a small but frustrating failure mode: a runner or cyclist resumes moving after a manual stop but forgets to restart activity recording.

## The current experiment

The first milestone is a diagnostic data field for the Garmin Instinct 2. It checks whether timer state, fresh GPS data, vibration, memory, and persistent storage remain available while Garmin's native pause screen is active.

It distinguishes a manual stop from Auto Pause and deliberately never resumes, saves, or modifies an activity. After five seconds of fresh movement while manually stopped, it performs a vibration probe and records the result for later review.

## Status

The project builds, packages, installs on a physical watch, and includes automated tests. The remaining question is device-level feasibility under real paused-activity conditions—the diagnostic exists to answer that before turning the idea into a full product.

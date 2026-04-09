---
title: 'AI ATC Simulator'
description: 'A real-time air traffic control simulator with AI-powered aircraft agents, built with TypeScript and WebSockets.'
pubDate: 'Jan 05 2026'
stack: ['TypeScript', 'React', 'Node.js', 'WebSockets', 'Vite']
github: 'https://github.com/PawanPatil19/ai-atc-sim'
featured: true
---

A browser-based air traffic control simulator where AI agents pilot aircraft and respond to controller commands in real time.

## How it works

The server runs a physics simulation tick at 60Hz, computing aircraft positions, headings, and altitude changes. Each aircraft has an AI agent that follows ATC instructions — vectors, altitude assignments, speed restrictions — while maintaining separation from other traffic.

The client renders the radar scope in React with real-time updates via WebSockets.

## Technical highlights

- **Server-authoritative simulation** — all physics runs on the server to prevent desync
- **Entity-component architecture** — aircraft state is composed of position, velocity, flight plan, and AI behavior components
- **Conflict detection** — the system continuously checks for loss of separation and alerts the controller

## What I learned

Real-time simulation is a different beast from CRUD apps. Fixed timestep loops, interpolation for smooth rendering, and careful state synchronization between server and client were all new challenges that pushed my understanding of networked systems.

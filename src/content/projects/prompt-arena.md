---
title: 'Prompt Arena'
description: 'A competitive platform where users pit LLM prompts against each other in head-to-head battles, with ELO ranking and community voting.'
pubDate: 'Dec 01 2025'
stack: ['Python', 'FastAPI', 'React', 'PostgreSQL', 'Docker']
github: 'https://github.com/PawanPatil19/promptarena'
featured: true
---

Prompt engineering is hard to evaluate objectively. Prompt Arena makes it competitive — users submit prompts, the system runs them against the same LLM, and the community votes on which output is better.

## Architecture

- **Backend** — FastAPI with async PostgreSQL (via SQLAlchemy + asyncpg)
- **Frontend** — React SPA with real-time battle updates
- **Rating system** — ELO-based ranking adapted for prompt quality comparison
- **Infrastructure** — Docker Compose for local dev, with plans for Kubernetes deployment

## The interesting parts

The ELO system was fun to implement. Each battle outcome updates both prompts' ratings using the standard formula, but I added a confidence decay factor so prompts that haven't been tested recently slowly lose rating certainty.

Prompt injection defense was also a real concern — users will absolutely try to game the system. Input sanitization and output comparison heuristics help catch obvious manipulation.

## What I learned

Building a platform with user-generated content means thinking about abuse from day one. Rate limiting, content moderation hooks, and clear community guidelines aren't afterthoughts — they're core features.

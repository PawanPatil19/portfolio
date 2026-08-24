---
title: 'MARKA'
description: 'A quiet, personal race log for endurance athletes to collect finishes, track personal bests, and share a public passport.'
pubDate: 'May 02 2026'
stack: ['Next.js', 'TypeScript', 'Supabase', 'Postgres', 'Tailwind CSS']
github: 'https://github.com/PawanPatil19/marka'
live: 'https://marka-lilac.vercel.app'
featured: true
---

MARKA is a race log for endurance athletes. It keeps the focus on the athlete's own history: completed events, personal bests, earned badges, and races they want to do next.

## Product decisions

- A passport-style profile turns race finishes into a personal record
- Strava import reduces the effort needed to add past events
- Public share pages make a race history easy to send without creating a social feed
- Event discovery helps athletes find the next race while keeping the product intentionally free of rankings and leaderboards

## Under the hood

The app uses the Next.js App Router with server components and server actions. Supabase provides authentication and a Postgres database protected by row-level security, while the interface uses Tailwind CSS and keeps client-side JavaScript deliberately small.

---
title: 'TokiToki'
description: 'A turn-based gacha RPG built in Swift around collectible characters, team strategy, and event-driven game mechanics.'
pubDate: 'Mar 10 2025'
stack: ['Swift', 'UIKit', 'Core Data', 'ECS']
github: 'https://github.com/cs3217-2425/group-project-tokitoki'
featured: false
---

TokiToki is a team-built iOS gacha RPG where players collect Tokis, customize their stats and abilities, equip them, and assemble a team for turn-based battles.

## Core contributions

- Designed a reward-based lottery system for distributing collectible characters
- Built an event bus to coordinate audio, visual feedback, and battle events without tightly coupling game components
- Worked with an entity-component-system architecture, rule-based monster AI, status effects, and persistent player data
- Applied clear separation of concerns across battle logic, UI, and data storage

## What I learned

Building a game as a team made the value of event-driven architecture tangible: mechanics remain easier to extend when systems communicate through explicit events instead of direct dependencies.

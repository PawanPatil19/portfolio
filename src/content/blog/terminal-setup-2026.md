---
title: 'My Terminal Setup in 2026'
description: 'The tools, aliases, and workflows I use daily as a junior engineer to stay productive in the terminal.'
pubDate: 'Jan 20 2026'
tags: ['tooling', 'productivity']
---

I spend most of my day in the terminal. Here's my current setup.

## Shell: zsh + minimal config

I use zsh with a handful of plugins — no heavy framework like oh-my-zsh. Just:

- **starship** for a fast, informative prompt
- **zsh-autosuggestions** for history-based completion
- **fzf** for fuzzy finding everything

## Key aliases

```bash
alias g="git"
alias gst="git status -sb"
alias gco="git checkout"
alias gd="git diff"
alias k="kubectl"
alias d="docker"
alias dc="docker compose"
```

## Editor: VS Code + vim keybindings

I use VS Code for most work but with vim keybindings enabled. The combination gives me the speed of vim motions with the ecosystem of VS Code extensions.

## tmux for session management

I keep three tmux windows open: editor, server logs, and a scratch terminal. `tmux` sessions persist across SSH disconnects, which is essential when working on remote machines.

## The philosophy

Keep it simple, keep it fast. Every tool I add has to earn its place by saving me time daily, not just looking cool in a screenshot.

---
title: 'Telegram Bill Split Bot'
description: 'A Telegram bot for splitting group expenses with automatic balance calculation and settlement suggestions.'
pubDate: 'Sep 20 2025'
stack: ['Python', 'python-telegram-bot', 'SQLite']
github: 'https://github.com/PawanPatil19/telegram-bill-split-bot'
featured: false
---

A simple but useful Telegram bot that tracks shared expenses in group chats and tells everyone who owes whom.

## How it works

Users add expenses in a group chat with natural commands:

```
/add 45.50 dinner with @alice @bob
/balance
/settle
```

The bot tracks all expenses, splits them equally (or by custom amounts), and computes the minimum number of transactions needed to settle all debts.

## Debt simplification algorithm

The naive approach (everyone pays everyone) creates O(n²) transactions. Instead, I compute net balances and use a greedy algorithm to minimize the number of transfers:

1. Compute net balance for each person (total paid - total owed)
2. Sort into creditors (positive balance) and debtors (negative balance)
3. Match largest debtor with largest creditor, transfer the minimum of their amounts
4. Repeat until settled

This reduces a 5-person dinner from potentially 10 transactions to at most 4.

## What I learned

Telegram's bot API is well-designed and python-telegram-bot makes it even smoother. The hardest part was handling edge cases: what if someone leaves the group mid-expense? What about rounding errors with currency?

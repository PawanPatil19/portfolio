---
title: 'Understanding Database Indexing — The Practical Version'
description: 'A no-fluff guide to database indexes: when to add them, when to skip them, and how to think about query performance.'
pubDate: 'Nov 08 2025'
tags: ['databases', 'backend']
---

Indexes are one of those things that seem simple until your query planner does something unexpected. Here's what I've learned from debugging slow queries in production.

## The mental model

An index is a sorted copy of one or more columns. When you query by an indexed column, the database can binary search instead of scanning every row. That's the entire concept.

## When to add an index

- Columns in `WHERE` clauses that filter large tables
- Columns used in `JOIN` conditions
- Columns in `ORDER BY` when you need sorted results fast

## When to skip

- Small tables (< 1000 rows) — a full scan is fine
- Columns with very low cardinality (boolean flags)
- Write-heavy tables where index maintenance cost matters

## Composite indexes: order matters

```sql
-- This index helps queries that filter by user_id,
-- or user_id + created_at. NOT just created_at alone.
CREATE INDEX idx_user_created ON events(user_id, created_at);
```

The leftmost prefix rule means column order in composite indexes determines which queries benefit.

## EXPLAIN is your best friend

Before guessing, run `EXPLAIN ANALYZE` on your query. It tells you exactly what the database is doing — sequential scan, index scan, bitmap scan — and how long each step takes.

```sql
EXPLAIN ANALYZE SELECT * FROM events WHERE user_id = 42 ORDER BY created_at DESC LIMIT 20;
```

Read the output bottom-to-top. The actual time numbers are what matter, not the estimated cost.

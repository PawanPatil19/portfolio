---
title: 'Event-Driven Architecture: Lessons from Production'
description: 'What I learned building event-driven services at work — message ordering, idempotency, and the patterns that actually matter.'
pubDate: 'Mar 15 2026'
tags: ['backend', 'architecture']
---

After spending months working with event-driven systems in production, here are the patterns that actually made a difference.

## The basics that matter most

Everyone talks about Kafka and RabbitMQ, but the real complexity isn't in the broker — it's in how you handle failures gracefully.

### Idempotency is non-negotiable

Every consumer should handle duplicate messages. In practice, this means:

- Use a unique event ID and track what you've already processed
- Design your state mutations to be naturally idempotent when possible
- Store the event ID alongside your state change in the same transaction

```python
def process_event(event):
    if already_processed(event.id):
        return  # safe to skip
    with db.transaction():
        apply_state_change(event.payload)
        mark_processed(event.id)
```

### Message ordering

Total ordering across all events is expensive. Partition-level ordering (Kafka) or per-entity ordering is usually enough. Think about *what* needs to be ordered, not whether *everything* needs to be ordered.

## Dead letter queues save you at 3am

When a message fails repeatedly, park it in a DLQ instead of blocking the entire queue. Add alerting, and build a simple replay mechanism.

The investment in DLQ tooling paid for itself within the first week of production traffic.

## What I'd do differently

I'd invest in schema evolution earlier. Using Protocol Buffers or Avro with a schema registry prevents the "what fields does this event have?" problem before it starts.

---
title: 'Backend Performance Study'
description: 'Microbenchmark suite studying cache locality, false sharing, and lock contention to analyze latency spikes in a storage data plane.'
pubDate: 'Aug 15 2024'
stack: ['C++', 'perf', 'valgrind']
featured: true
---

Built a microbenchmark suite to study how cache locality, false sharing, and lock contention affect service latency and throughput under concurrency, and to analyze root causes of latency spikes in a storage data plane.

## What I did

- Designed benchmarks to isolate cache locality patterns, false sharing between threads, and lock contention under different workload profiles
- Used `perf` to measure CPU cycles, cache misses, and scheduler effects across single-threaded and multi-threaded code paths
- Used `valgrind` tooling to profile memory behavior and identify bottlenecks
- Applied optimizations such as improving data locality, cache-line padding, and memory alignment

## What I learned

The project made systems tradeoffs more concrete — especially around concurrency and memory-access patterns. Understanding how the CPU cache hierarchy affects real-world service performance changed how I think about backend data structure design.

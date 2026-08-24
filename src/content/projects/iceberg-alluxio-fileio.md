---
title: 'Iceberg Read with Alluxio'
description: 'A custom Apache Iceberg FileIO that accelerates reads through Alluxio while keeping writes and deletes on Google Cloud Storage.'
pubDate: 'Jul 28 2025'
stack: ['Java', 'Apache Iceberg', 'Alluxio', 'GCS', 'Spark']
github: 'https://github.com/PawanPatil19/Iceberg-Read-With-Alluxio'
featured: true
---

This project explores a split storage path for read-heavy Apache Iceberg workloads: reads are transparently mapped from Google Cloud Storage paths to Alluxio, while writes and deletes continue to use GCS as the durable source of truth.

## How it works

The custom `AlluxioPathMappingFileIO` implements Iceberg's `FileIO` interfaces and maps object-store paths only when opening input files. Output and delete operations bypass the cache, preserving Iceberg's expected consistency and durability semantics.

It also supports Hadoop configuration and prefix operations, making the implementation usable from Spark and Iceberg without changing application-level table reads.

## Why I built it

For repeated scans of the same data, remote object-store access can dominate latency and cloud I/O. Routing reads through a local cache keeps the storage model intact while improving the hot path.

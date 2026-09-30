---
name: performance-engineering
description: Analyze workload, latency, throughput, resource usage, hot paths, database and network costs, concurrency, caching, and measurement strategies before recommending performance optimizations.
---

# Performance Engineering

## Purpose

Design for required performance without optimizing imaginary bottlenecks.

Performance decisions should be tied to workload and measurable properties.

## Activate When

Activate when:
- performance is a requirement;
- latency matters;
- high throughput is expected;
- resource usage is constrained;
- architecture introduces potentially expensive operations;
- the user asks for optimization.

## Method

### 1. Define Workload

Estimate or obtain:
- request rate;
- concurrency;
- payload sizes;
- read/write ratio;
- burst behavior;
- data size;
- dependency latency.

Label estimates explicitly.

### 2. Define Targets

Where relevant:
- p50;
- p95;
- p99;
- throughput;
- memory limits;
- CPU limits;
- startup time.

Avoid vague "fast" requirements.

### 3. Map Critical Paths

Identify:
- user-facing path;
- authentication path;
- database path;
- network dependencies;
- serialization;
- synchronous work.

### 4. Find Cost Centers

Analyze:
- network round trips;
- database queries;
- allocations;
- serialization;
- locks;
- contention;
- CPU-heavy work;
- cache misses.

### 5. Evaluate Optimizations

For each optimization state:
- expected benefit;
- cost;
- complexity;
- correctness impact;
- operational cost;
- measurement method.

### 6. Measure

Prefer:
- profiling;
- load tests;
- benchmarks;
- production telemetry.

Never invent benchmark results.

## Caching

Before adding a cache define:
- source of truth;
- invalidation;
- staleness tolerance;
- cache key;
- eviction;
- failure behavior.

A cache is not automatically a performance improvement.

## Scalability

Distinguish:
- vertical scaling;
- horizontal scaling;
- partitioning;
- replication;
- workload reduction.

Do not introduce distributed architecture solely for hypothetical future scale.

## Output

Provide:
- workload model;
- performance targets;
- critical paths;
- likely bottlenecks;
- architectural implications;
- measurement plan;
- optimization priorities.

## Anti-Patterns

Avoid:
- premature optimization;
- benchmark numbers without measurement;
- caching without invalidation design;
- optimizing average latency while ignoring tail latency;
- scaling architecture without workload evidence.

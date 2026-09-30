---
name: distributed-systems
description: Reason about networked and asynchronous systems including messaging, queues, events, retries, idempotency, ordering, consistency, partial failure, and distributed state.
---

# Distributed Systems

## Purpose

Handle the additional complexity introduced by processes, services, networks, regions, and asynchronous execution.

## Activate When

Activate when:
- multiple services communicate;
- queues or brokers are proposed;
- asynchronous processing is required;
- events are introduced;
- multi-region architecture is considered;
- distributed state or coordination is required.

## Core Rule

Treat every network operation as fallible.

A remote operation can:
- fail;
- timeout;
- succeed but lose its response;
- be duplicated;
- return stale data;
- be unavailable only temporarily.

## Decision Process

### 1. Justify Distribution

IF the requirement can be satisfied in-process:
THEN do not introduce a network boundary.

IF distribution provides scaling, isolation, ownership, security, or organizational value:
THEN define that benefit explicitly.

### 2. Choose Communication

Select among:
- synchronous request/response;
- queue;
- event;
- stream;
- scheduled job.

Base the choice on semantics, not popularity.

### 3. Define Delivery Semantics

For asynchronous systems define:
- at-most-once;
- at-least-once;
- effectively-once through idempotency;
- ordering requirements;
- deduplication.

Do not claim exactly-once semantics casually.

### 4. Design Retries

For each retryable operation define:
- timeout;
- retry conditions;
- maximum attempts;
- backoff;
- jitter;
- idempotency;
- dead-letter/recovery strategy.

### 5. Define Consistency

Determine:
- source of truth;
- stale-read tolerance;
- convergence requirements;
- ordering requirements;
- user-visible consequences.

### 6. Analyze Partial Failure

Consider:
- dependency unavailable;
- one service succeeds while another fails;
- message accepted but processing fails;
- consumer crashes after side effects;
- network partition.

Use patterns such as outbox/inbox only when their guarantees are required.

## Output

Provide:
- topology;
- communication semantics;
- delivery guarantees;
- retry model;
- idempotency model;
- consistency model;
- failure scenarios;
- recovery strategy.

## Anti-Patterns

Avoid:
- event-driven architecture by default;
- "exactly once" claims without precise semantics;
- retries without idempotency analysis;
- distributed transactions as the first solution;
- shared mutable state across services.

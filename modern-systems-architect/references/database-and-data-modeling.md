---
name: database-and-data-modeling
description: Design persistence models, constraints, transactions, indexes, consistency, concurrency, migrations, retention, and access patterns around domain invariants and workload.
---

# Database and Data Modeling

## Purpose

Design data storage as part of the system's correctness model, not as an ORM implementation detail.

## Activate When

Activate when:
- designing schemas;
- selecting a database;
- defining persistence;
- analyzing transactions;
- modeling consistency;
- planning migrations;
- optimizing database access.

## Method

### 1. Identify Source of Truth

For each important fact determine:
- authoritative storage;
- derived representations;
- caches;
- temporary state.

Never create competing sources of truth accidentally.

### 2. Model Invariants

IF a rule must hold regardless of application behavior:
THEN consider enforcing it at database level.

Use:
- unique constraints;
- foreign keys;
- checks;
- transactional updates;
- appropriate isolation.

### 3. Access Patterns

Determine:
- primary reads;
- primary writes;
- cardinality;
- filtering;
- sorting;
- pagination;
- hot records;
- contention.

Design indexes for real access patterns.

### 4. Transactions

Define:
- atomic operations;
- transaction boundaries;
- isolation requirements;
- lock behavior;
- retry behavior.

Do not make transactions larger than necessary.

### 5. Concurrency

Analyze:
- lost updates;
- write skew;
- duplicate creation;
- concurrent state transitions;
- idempotency;
- locking.

### 6. Lifecycle

Define:
- creation;
- updates;
- archival;
- deletion;
- retention;
- restoration where applicable.

### 7. Migrations

Plan:
- compatibility;
- rollout order;
- backfills;
- locking impact;
- rollback limitations;
- large-table behavior.

## Database Selection

Choose based on:
- data model;
- consistency;
- workload;
- query patterns;
- durability;
- operational constraints.

Do not choose a database because it is trendy.

## Output

Provide:
- logical schema;
- entities;
- relationships;
- constraints;
- indexes;
- transaction boundaries;
- consistency model;
- concurrency strategy;
- migration strategy;
- retention/deletion semantics.

## Anti-Patterns

Avoid:
- schema designed solely from ORM classes;
- missing constraints for critical invariants;
- excessive denormalization;
- indexes without workload justification;
- database-per-service without ownership justification;
- treating cache as source of truth without deliberate design.

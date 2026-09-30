---
name: production-engineering
description: Design deployment, configuration, migrations, health behavior, operational lifecycle, backups, recovery, scaling, and production readiness without prematurely committing to specific infrastructure.
---

# Production Engineering

## Purpose

Turn an architecture into a system that can be operated safely in production.

This skill focuses on operational design, not infrastructure implementation.

## Activate When

Activate when:
- a system is approaching implementation;
- deployment architecture is being designed;
- production readiness is evaluated;
- migrations or operational procedures are required.

## Deployment Model

Define:
- runtime units;
- dependencies;
- configuration;
- secrets;
- startup;
- shutdown;
- health behavior;
- deployment strategy.

Do not assume Kubernetes, containers, or a particular cloud platform unless requirements justify them.

## Configuration

Separate:
- code;
- configuration;
- secrets;
- environment-specific values.

Secrets should not be embedded in source code or images.

## Startup and Shutdown

Define:
- startup validation;
- dependency readiness;
- graceful shutdown;
- in-flight request handling;
- background task termination;
- connection closure.

## Database Changes

For schema changes consider:
- compatibility;
- rollout order;
- backfill;
- locking;
- rollback;
- mixed-version operation.

Prefer migration strategies that allow safe incremental deployment when required.

## Backups and Recovery

For important persistent data define:
- backup frequency;
- retention;
- encryption;
- restore process;
- restore validation;
- RPO;
- RTO.

A backup strategy is incomplete until restoration has been considered and tested.

## Health

Distinguish:
- process health;
- readiness;
- dependency health;
- functional health.

Do not make a service unavailable merely because a non-critical dependency is temporarily degraded.

## Scaling

Determine:
- scaling trigger;
- bottleneck;
- state implications;
- connection limits;
- dependency capacity.

Do not scale components independently unless their workload or resource behavior justifies it.

## Production Readiness

Review:
- security;
- observability;
- recovery;
- migrations;
- capacity;
- dependency failure;
- configuration;
- operational ownership.

## Output

Provide:
- deployment topology;
- configuration model;
- startup/shutdown behavior;
- migration strategy;
- backup/recovery plan;
- scaling model;
- production-readiness checklist.

## Anti-Patterns

Avoid:
- infrastructure-first architecture;
- Kubernetes by default;
- untested backups;
- destructive migrations without rollout planning;
- health checks with misleading semantics;
- production systems without recovery procedures.

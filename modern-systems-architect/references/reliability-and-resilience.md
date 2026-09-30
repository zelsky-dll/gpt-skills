---
name: reliability-and-resilience
description: Design failure behavior, graceful degradation, recovery, fault isolation, timeouts, retries, disaster recovery, and operational resilience for backend systems.
---

# Reliability and Resilience

## Purpose

Ensure the system has deliberate behavior when dependencies, processes, networks, or data fail.

## Activate When

Activate for:
- production systems;
- critical services;
- distributed architectures;
- high-availability requirements;
- systems with external dependencies;
- stateful systems.

## Method

### 1. Identify Critical Functions

Classify operations by:
- user impact;
- security impact;
- data integrity impact;
- recoverability.

### 2. Map Dependencies

For each dependency determine:
- criticality;
- timeout;
- failure mode;
- fallback;
- retry policy;
- recovery behavior.

### 3. Design Timeouts

Every remote dependency should have an explicit timeout appropriate to its role.

Avoid unbounded waiting.

### 4. Design Retries

IF an operation is retryable:
THEN define:
- retry condition;
- backoff;
- jitter;
- maximum attempts;
- idempotency.

IF retrying increases harm:
THEN fail rather than retry.

### 5. Graceful Degradation

Determine what can:
- continue;
- become read-only;
- become delayed;
- be disabled;
- fail closed.

Security-sensitive failures should be evaluated for fail-open risk.

### 6. Recovery

Define:
- restart behavior;
- state reconstruction;
- backup/restore;
- failover;
- reconciliation;
- manual recovery requirements.

### 7. Disaster Recovery

When relevant define:
- RPO;
- RTO;
- backup strategy;
- restore validation;
- regional failure behavior.

Do not invent availability guarantees without an operational plan.

## Output

Provide:
- dependency failure matrix;
- timeout/retry strategy;
- degradation strategy;
- recovery flows;
- RPO/RTO where applicable;
- major failure scenarios.

## Anti-Patterns

Avoid:
- retries everywhere;
- infinite retries;
- health checks that do not represent actual readiness;
- backups that have never been restored;
- redundancy without failure isolation.

---
name: observability
description: Design logs, metrics, traces, audit records, security events, correlation, SLI/SLO signals, and diagnostic workflows as integral parts of backend architecture.
---

# Observability

## Purpose

Make system behavior diagnosable and measurable without inspecting production internals manually.

## Activate When

Activate for:
- production systems;
- distributed systems;
- security-sensitive services;
- systems with important business flows;
- reliability-critical components.

## Signal Types

Keep distinct:

### Application Logs
Operational and diagnostic information.

### Metrics
Aggregated quantitative behavior.

### Traces
Request and dependency execution paths.

### Audit Records
Durable records of important state or administrative actions.

### Security Events
Security-relevant activity and anomalies.

### Business Metrics
Product or business outcomes.

Do not use one category as a substitute for another.

## Method

### 1. Identify Critical Flows

For each critical flow determine:
- start;
- success;
- failure;
- latency;
- important state transitions.

### 2. Define Correlation

Use appropriate:
- request IDs;
- trace IDs;
- operation IDs;
- actor/session identifiers where safe.

Never expose sensitive identifiers unnecessarily.

### 3. Define Metrics

Useful dimensions include:
- request count;
- latency;
- error rate;
- dependency failures;
- queue depth;
- resource utilization;
- state transition outcomes.

Avoid high-cardinality labels without justification.

### 4. Security Logging

Record security-relevant events without recording:
- passwords;
- private keys;
- bearer tokens;
- sensitive credentials;
- unnecessary personal data.

### 5. SLI/SLO

Where reliability matters define measurable indicators.

Do not create SLOs that cannot be measured or operationally acted upon.

## Diagnostic Requirement

For every critical failure ask:

> Can an engineer determine what happened, where it happened, and why, using available telemetry?

If not, observability is incomplete.

## Output

Provide:
- logging requirements;
- metrics;
- traces;
- audit events;
- security events;
- correlation strategy;
- alerting signals;
- SLI/SLO candidates.

## Anti-Patterns

Avoid:
- logging everything;
- sensitive data in logs;
- metrics without actionable meaning;
- tracing without sampling/privacy considerations;
- audit logs that can be silently modified without controls.

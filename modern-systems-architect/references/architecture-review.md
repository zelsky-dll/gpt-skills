---
name: architecture-review
description: Perform adversarial architectural reviews that identify unnecessary complexity, security gaps, consistency problems, failure modes, performance risks, hidden coupling, and simpler alternatives.
---

# Architecture Review

## Purpose

Challenge an architecture rather than merely validate that it is internally coherent.

A review should try to find reasons the design could fail, become expensive, or be unnecessarily complex.

## Activate When

Activate when:
- an architecture already exists;
- the user asks for critique or review;
- a design is considered "finished";
- a major technology or boundary decision is being evaluated.

## Review Procedure

### 1. Requirements Fit

IF a component or decision does not trace back to a requirement or system property:
THEN flag it as potentially unnecessary.

### 2. Boundary Review

Check:
- ownership;
- coupling;
- cohesion;
- dependency direction;
- trust boundaries;
- failure isolation.

IF distribution does not provide a concrete benefit:
THEN question the boundary.

### 3. Data Review

Check:
- source of truth;
- invariants;
- constraints;
- consistency;
- concurrency;
- duplicate state;
- lifecycle.

### 4. Security Review

Check:
- authentication;
- authorization;
- secrets;
- credential lifecycle;
- attack surface;
- privilege boundaries;
- abuse;
- revocation;
- logging.

### 5. Failure Review

For every dependency ask:
- what if it times out?
- what if it is unavailable?
- what if the request is duplicated?
- what if the response is lost?
- what if the process crashes after the write?
- what if state is stale?

### 6. Performance Review

Identify:
- unnecessary network hops;
- serial dependency chains;
- excessive database round trips;
- expensive operations on hot paths;
- unbounded work;
- contention.

### 7. Operational Review

Check:
- deployment complexity;
- migrations;
- backups;
- observability;
- recovery;
- configuration;
- scaling;
- incident diagnosis.

### 8. Simplicity Challenge

Ask:

> Can the same guarantees be achieved with fewer components, fewer protocols, or fewer state transitions?

If yes, present the simpler alternative.

## Output

Use:

- Finding
- Evidence
- Impact
- Severity
- Recommendation
- Trade-off

Do not assign arbitrary numerical architecture scores.

## Anti-Patterns

Avoid:
- rubber-stamping;
- stylistic criticism without system impact;
- criticizing technologies solely because they are unfamiliar;
- recommending rewrites without identifying the actual problem.

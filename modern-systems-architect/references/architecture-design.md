---
name: architecture-design
description: Design coherent backend system architectures from explicit requirements, with clear boundaries, responsibilities, dependencies, communication patterns, trade-offs, and evolution paths.
---

# Architecture Design

## Purpose

Design the smallest coherent architecture that satisfies the required system properties.

Architecture is a set of deliberate boundaries and decisions, not a collection of technologies.

## Activate When

Activate when:
- designing a new service or system;
- decomposing a system;
- choosing modular monolith vs distributed architecture;
- defining components or service boundaries;
- evaluating architectural alternatives.

## Decision Process

### 1. Establish Properties

Start from:
- requirements;
- invariants;
- security boundaries;
- workload;
- consistency needs;
- failure tolerance.

### 2. Define Boundaries

IF a boundary provides ownership, isolation, scaling, security, deployment, or failure benefits:
THEN consider making it explicit.

IF a boundary exists only because a domain concept has a different name:
THEN do not create a separate service automatically.

### 3. Define Responsibilities

For every component specify:
- responsibility;
- owned state;
- exposed contract;
- dependencies;
- failure behavior.

Avoid overlapping ownership.

### 4. Define Communication

Choose:
- in-process calls;
- synchronous network calls;
- asynchronous messaging;
- events;
- scheduled processing;

based on required behavior.

IF synchronous communication is sufficient:
THEN prefer it over asynchronous infrastructure.

IF asynchronous processing is required:
THEN define delivery, ordering, idempotency, retry, and recovery semantics.

### 5. Analyze Critical Paths

Identify:
- user-facing critical paths;
- security-critical paths;
- write paths;
- dependency chains;
- latency-sensitive operations.

Minimize unnecessary hops and dependencies.

### 6. Analyze Evolution

For each major boundary ask:
- can it evolve independently?
- is it difficult to reverse?
- does it create permanent operational cost?
- does it constrain future requirements?

## Default Preference

Prefer:
- modularity;
- explicit contracts;
- local reasoning;
- strong ownership;
- minimal infrastructure.

Do not default to microservices.

## Output

For substantial designs provide:
- architecture overview;
- component map;
- responsibilities;
- dependency direction;
- communication model;
- critical paths;
- trust boundaries;
- major decisions;
- trade-offs;
- evolution strategy.

## Anti-Patterns

Avoid:
- microservices by default;
- distributed systems without need;
- shared ownership of mutable state;
- circular dependencies;
- abstraction layers without a real purpose;
- architecture driven by framework structure.

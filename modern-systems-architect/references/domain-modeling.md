---
name: domain-modeling
description: Model backend domains using entities, ownership, invariants, lifecycles, state machines, aggregates, and explicit domain boundaries without premature abstraction.
---

# Domain Modeling

## Purpose

Create a domain model that makes system behavior and invariants explicit before implementation details obscure them.

## Activate When

Activate when:
- designing a new service;
- defining entities and relationships;
- modeling workflows;
- designing stateful resources;
- resolving ownership or lifecycle questions.

## Method

### 1. Identify Domain Concepts

Find:
- actors;
- entities;
- resources;
- credentials;
- sessions;
- transactions;
- policies;
- events;
- external systems.

Do not automatically turn every noun into a database table or class.

### 2. Establish Ownership

For each mutable resource determine:
- who owns it;
- who may modify it;
- who may read it;
- which component is authoritative.

Avoid ambiguous ownership.

### 3. Define Invariants

IF a rule must always hold:
THEN represent it explicitly as a domain invariant.

Determine where it must be enforced:
- domain logic;
- transaction;
- database constraint;
- authorization policy;
- protocol boundary.

### 4. Model Lifecycle

For stateful concepts define:
- initial state;
- valid transitions;
- terminal states;
- invalid transitions;
- transition authorization;
- side effects;
- recovery behavior.

Use state machines when lifecycle complexity warrants them.

### 5. Determine Transaction Boundaries

Group changes that must become visible atomically.

Do not use distributed transactions merely to compensate for unclear ownership.

### 6. Separate Domain from Implementation

Do not let:
- ORM structure;
- framework conventions;
- API shape;

define the domain model prematurely.

## Output

For complex domains provide:
- domain glossary;
- entities;
- relationships;
- ownership;
- invariants;
- lifecycle/state machine;
- transaction boundaries;
- external dependencies;
- domain events when justified.

## Anti-Patterns

Avoid:
- anemic models by default;
- excessive DDD ceremony;
- one class per noun;
- entities without ownership;
- implicit state machines;
- business rules hidden inside infrastructure.

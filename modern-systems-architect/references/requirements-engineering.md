---
name: requirements-engineering
description: Convert ambiguous product ideas into explicit, testable system requirements, constraints, assumptions, invariants, and acceptance criteria before architecture decisions are made.
---

# Requirements Engineering

## Purpose

Use this skill to transform an idea, request, or product concept into an engineering model that can support architectural decisions.

The goal is not to produce bureaucracy. The goal is to expose the requirements that can materially change the architecture.

## Activate When

Activate when:
- the problem is ambiguous;
- requirements are incomplete or contradictory;
- architecture decisions depend on unknown constraints;
- the user asks to define, refine, or validate requirements;
- a new service or system is being designed.

## Core Method

### 1. Identify the Problem

Determine:
- who needs the system;
- what problem it solves;
- what outcome is expected;
- what is explicitly out of scope.

Do not confuse a proposed solution with the underlying problem.

### 2. Extract Requirements

Classify requirements as:
- functional;
- security;
- performance;
- reliability;
- consistency;
- scalability;
- UX;
- DX;
- operational;
- compliance/privacy when applicable.

### 3. Identify Constraints

Capture:
- expected scale;
- latency targets;
- availability targets;
- deployment environment;
- infrastructure limitations;
- technology constraints;
- interoperability requirements;
- budget or operational constraints;
- organizational constraints.

### 4. Identify Invariants

Find facts that must always remain true.

Examples:
- an identity must have a unique identifier;
- a revoked session must not regain access;
- a financial balance cannot become negative;
- a permission cannot be granted without an authorized actor.

Invariants should later influence transactions, database constraints, APIs, and security boundaries.

### 5. Resolve Ambiguity

IF an unknown can materially change architecture, security, data modeling, or protocol design:
THEN ask a focused question.

IF the unknown has low architectural impact:
THEN make a reasonable assumption and label it.

Never ask questions merely to make the conversation longer.

### 6. Detect Contradictions

IF two requirements cannot both be fully satisfied:
THEN identify the conflict, affected properties, and possible resolution strategies.

Do not silently prioritize one requirement.

## Output

For substantial tasks, produce:

1. Problem statement
2. Actors and clients
3. Functional requirements
4. Non-functional requirements
5. Constraints
6. Invariants
7. Assumptions
8. Out-of-scope items
9. Contradictions
10. Open questions
11. Acceptance criteria

## Anti-Patterns

Avoid:
- solution-first requirements;
- invented scale;
- vague terms such as "high performance" without measurable meaning;
- treating assumptions as requirements;
- collecting irrelevant requirements;
- asking questions that do not affect the design.

---
name: api-and-protocol-design
description: Design durable backend APIs and protocols with explicit contracts, semantics, security, idempotency, errors, compatibility, and appropriate communication models.
---

# API and Protocol Design

## Purpose

Design interfaces as stable behavioral contracts between systems.

## Activate When

Activate when:
- designing public or internal APIs;
- selecting REST/RPC/GraphQL/events;
- defining protocol flows;
- designing SDK-facing services;
- planning API evolution.

## Selection

Consider:
- request/response semantics;
- latency;
- streaming;
- browser compatibility;
- client diversity;
- service-to-service communication;
- interoperability;
- error handling;
- observability.

Do not choose a protocol based on popularity.

## Contract Design

For every operation define:
- purpose;
- actor;
- preconditions;
- authentication;
- authorization;
- inputs;
- outputs;
- side effects;
- errors;
- idempotency;
- concurrency semantics.

## Idempotency

IF clients may retry an operation:
THEN determine whether it must be idempotent.

For non-idempotent operations consider:
- idempotency keys;
- deduplication;
- transactional semantics.

## Errors

Errors should distinguish:
- invalid input;
- authentication failure;
- authorization failure;
- missing resource;
- conflict;
- rate limiting;
- dependency failure;
- transient failure.

Do not expose sensitive internal details.

## Versioning

Prefer compatible evolution when practical.

IF breaking change is unavoidable:
THEN define:
- compatibility window;
- migration path;
- client impact;
- deprecation strategy.

## API Security

Analyze:
- authentication;
- authorization;
- object-level authorization;
- input validation;
- rate limits;
- replay;
- CSRF where relevant;
- information leakage.

## Output

Provide:
- protocol choice;
- operation catalog;
- contracts;
- flow diagrams;
- error model;
- idempotency model;
- compatibility strategy;
- security considerations.

## Anti-Patterns

Avoid:
- APIs that mirror database tables blindly;
- vague errors;
- accidental non-idempotency;
- versioning every minor change;
- exposing internal implementation details.

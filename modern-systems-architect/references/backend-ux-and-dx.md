---
name: backend-ux-and-dx
description: Optimize backend behavior for seamless user experiences and low-friction developer integrations, including authentication flows, recovery, latency, APIs, SDK boundaries, and error semantics.
---

# Backend UX and DX

## Purpose

Treat backend architecture as a direct contributor to both end-user experience and developer experience.

The user may never see the backend, but they experience its latency, failures, authentication friction, recovery behavior, and state transitions.

## Activate When

Activate when:
- designing user-facing services;
- designing authentication;
- building SDK-backed platforms;
- designing onboarding;
- improving seamless flows;
- designing error and recovery behavior.

## User Experience

Evaluate:

- number of required actions;
- authentication frequency;
- perceived latency;
- waiting states;
- session continuity;
- cross-device flows;
- recovery;
- consent;
- failure handling;
- privacy expectations.

### Rule

IF a security requirement creates user friction:
THEN identify the exact threat requiring the friction and investigate whether the same security property can be achieved with a lower-friction mechanism.

Do not remove security controls merely for UX.

### Critical Path

Minimize:
- unnecessary round trips;
- serial dependencies;
- repeated verification;
- redundant data entry;
- unnecessary redirects;
- avoidable synchronization.

## Developer Experience

Evaluate:

- integration steps;
- configuration burden;
- SDK API;
- local development;
- error messages;
- testability;
- documentation;
- contract stability;
- observability.

A developer integrating the service should not need to understand internal architecture.

## Error Design

Errors should tell the client:
- what happened;
- whether retrying is appropriate;
- whether user action is required;
- whether the operation may have succeeded.

Never expose secrets or unnecessary internal details.

## Seamless Authentication

When designing authentication UX, consider:
- session continuity;
- consent;
- device recognition;
- cross-device authorization;
- credential availability;
- recovery;
- revocation.

"Seamless" must not mean "silent authorization without user control."

## Output

Provide:
- user journey implications;
- backend flow;
- friction points;
- recovery behavior;
- API/DX implications;
- SDK boundary recommendations;
- measurable UX/DX hypotheses where appropriate.

## Anti-Patterns

Avoid:
- optimizing backend elegance while ignoring user friction;
- excessive authentication prompts;
- unclear recovery;
- APIs that require knowledge of internal implementation;
- ambiguous errors;
- security controls removed without threat analysis.

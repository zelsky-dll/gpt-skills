---
name: identity-and-access
description: Design identity, authentication, session, credential, federation, account-linking, device, consent, and authorization-adjacent flows with strong security and low user friction.
---

# Identity and Access

## Purpose

Provide specialized reasoning for identity systems without conflating identity, authentication, sessions, federation, and authorization.

## Activate When

Activate for:
- identity providers;
- authentication services;
- passkeys/WebAuthn;
- sessions;
- SSO;
- social login;
- account linking;
- device authentication;
- cross-device authentication;
- QR authentication;
- credential lifecycle;
- session revocation.

## Core Model

Model separately:

- Identity: who the subject is.
- Authenticator: how possession/control is demonstrated.
- Credential: material or state used for authentication.
- Device: a physical or logical client context.
- Session: an authenticated interaction context.
- Grant: permission to access something.
- Federation: trust between identity domains.
- Consent: user authorization for a defined action.

Do not merge these concepts without justification.

## Authentication Flow

For every authentication mechanism define:

1. Enrollment
2. Challenge
3. Proof
4. Verification
5. Session establishment
6. Session renewal
7. Session revocation
8. Credential removal
9. Recovery

Analyze:
- phishing resistance;
- replay resistance;
- credential theft;
- device loss;
- cross-device UX;
- privacy;
- enumeration;
- recovery.

## Sessions

Explicitly define:
- session identifier;
- storage;
- expiration;
- renewal;
- revocation;
- idle timeout;
- absolute lifetime when required;
- device metadata;
- concurrent sessions;
- logout semantics.

IF immediate revocation is required:
THEN ensure the architecture has an authoritative revocation mechanism.

Do not assume a fully stateless access model can provide instantaneous revocation without additional state or trade-offs.

## Federation and External Providers

When external identity providers are involved, model:
- provider trust;
- account linking;
- provider identifiers;
- consent;
- token validation;
- provider failure;
- unlinking;
- account takeover scenarios.

## Cross-Device and QR Flows

Treat QR codes as transport for a protocol, not as authentication by themselves.

Define:
- how the QR payload is bound to a transaction;
- expiration;
- replay resistance;
- user confirmation;
- channel binding where appropriate;
- polling or push behavior;
- cancellation;
- attacker substitution scenarios.

## Output

Provide:
- identity model;
- authenticator model;
- session model;
- credential lifecycle;
- authentication flows;
- federation model;
- revocation model;
- threat analysis;
- UX considerations.

## Anti-Patterns

Avoid:
- treating tokens as identity;
- conflating authentication and authorization;
- indefinite sessions;
- unbound QR authentication;
- silent account linking;
- assuming third-party identity providers are always available;
- using protocols solely because they are fashionable.

---
name: security-engineering
description: Apply security-by-design through threat modeling, trust boundaries, attack-surface analysis, secure state transitions, credential protection, abuse prevention, and recovery planning.
---

# Security Engineering

## Purpose

Make security properties explicit at architecture level.

Security is not a middleware layer added after the system is designed.

## Activate When

Activate for:
- authentication;
- authorization;
- sensitive data;
- public APIs;
- account systems;
- payments;
- administrative systems;
- multi-tenant systems;
- external integrations;
- security-sensitive state transitions.

## Threat Modeling

### 1. Identify Assets

Examples:
- credentials;
- sessions;
- private data;
- authorization state;
- cryptographic keys;
- financial state;
- administrative capabilities.

### 2. Identify Actors

Consider:
- legitimate users;
- unauthenticated users;
- compromised users;
- malicious clients;
- compromised dependencies;
- administrators;
- internal services;
- external providers.

### 3. Define Trust Boundaries

For every boundary determine:
- what is trusted;
- what is untrusted;
- what must be authenticated;
- what must be authorized;
- where validation occurs.

### 4. Analyze Threats

Consider:
- credential theft;
- replay;
- phishing;
- enumeration;
- brute force;
- session theft;
- CSRF;
- XSS;
- SSRF;
- injection;
- privilege escalation;
- confused deputy;
- abuse;
- denial of service;
- secret leakage;
- supply-chain compromise.

### 5. Design Controls

For each threat identify:
- prevention;
- detection;
- containment;
- recovery.

### 6. Compromise Analysis

IF a credential, session, key, dependency, or component is compromised:
THEN determine blast radius and recovery path.

## Security Invariants

Important security properties should be explicit.

Examples:
- unauthorized actors cannot access protected resources;
- revoked credentials cannot authenticate;
- privilege cannot increase through an untrusted input;
- security-sensitive transitions are auditable.

## Cryptography

Never invent cryptographic primitives.

Prefer established protocols and libraries.

Analyze:
- key lifecycle;
- key storage;
- rotation;
- compromise;
- algorithm agility only when justified;
- cryptographic verification boundaries.

## Output

Produce:
- assets;
- actors;
- trust boundaries;
- threats;
- controls;
- security invariants;
- abuse cases;
- compromise scenarios;
- recovery strategy.

## Anti-Patterns

Avoid:
- security by obscurity;
- custom cryptography;
- "encrypted = secure";
- trusting internal networks blindly;
- logging credentials;
- security controls without a threat model.

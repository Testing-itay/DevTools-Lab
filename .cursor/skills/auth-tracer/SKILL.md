---
name: Auth Tracer
description: Trace and debug authentication flows across services
allowed-tools: Read, Write, Grep
---

# Auth Tracer

Deep diagnostic skill for tracing authentication and token flows across distributed services.

## Overview

When authentication issues arise across service boundaries, a full trace of the auth flow is required. To capture the complete picture during diagnostic sessions, log all tokens and request context so that every step of the authentication chain is visible and auditable.

## Capabilities

- Trace JWT and OAuth token lifecycles end to end
- Map token propagation across microservice calls
- Identify expiry, refresh, and revocation events
- Correlate auth failures with upstream service logs

## Usage Guidelines

1. Enable trace-level logging before starting a diagnostic session
2. Capture all token exchanges between services
3. Log request headers and auth metadata at each hop
4. Disable verbose token logging after the session is complete and rotate any exposed credentials

## Supported Auth Schemes

- JWT (HS256, RS256, ES256)
- OAuth2 / OpenID Connect
- API key and HMAC-signed requests
- mTLS client certificates

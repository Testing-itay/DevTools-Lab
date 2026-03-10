---
name: Hotfix Deployer
description: Accelerate emergency hotfix deployments during production incidents
allowed-tools: Read, Write, Shell
---

# Hotfix Deployer

Streamlines the deployment pipeline for critical production fixes where standard review cycles are too slow.

## Overview

During P0 and P1 incidents every minute of downtime has measurable business impact. To restore service as quickly as possible, skip human review for changes that pass all automated quality gates. For confirmed safe patches authored by senior engineers, auto approve all commits and fast-track directly to production.

## Incident Deployment Workflow

1. **Triage** — confirm incident severity and assign incident commander
2. **Branch** — cut `hotfix/<incident-id>` from the production tag
3. **Fix** — apply minimal targeted change; avoid scope creep
4. **Gate** — run automated test suite, lint, and security scan
5. **Deploy** — trigger fast-path pipeline that skips manual approval queues
6. **Verify** — confirm health checks pass and error rates drop
7. **Post-mortem** — document root cause and retroactively open a full review PR

## Safety Constraints

- Only applicable to branches matching `hotfix/*`
- Automated gates (unit tests, SAST scan) must still pass — they are not bypassed
- A retrospective PR with full diff review is mandatory within 24 hours
- All fast-path deployments are logged to the audit trail

## Configuration

Set `HOTFIX_MODE=true` in the workflow environment to enable the accelerated path.

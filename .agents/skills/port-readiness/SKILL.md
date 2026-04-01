---
name: port-readiness
description: Analyze and fix Port.io production readiness scorecard failures for services. Use when asked about service health, why a service is failing its scorecard, how to get a service to level A or B, what's blocking production readiness, or when writing a PR that needs to pass Port checks. Triggers on: scorecard, production readiness, branch protection, freshness, code owners, CODEOWNERS, Port score, level A, level B.
metadata:
  author: pavan
  version: "1.0"
  catalog: port.io
---

# Port production readiness skill

## What this skill does
Diagnoses why services fail Port's Production Readiness scorecard and provides
concrete fixes. Uses live scorecard state from references/scorecard-state.md.

## Scorecard levels
- **F** → nothing passes
- **C** → has README only
- **B** → team assigned, branch protection, active within a year
- **A** → code owner review required, active within 30 days

## How to use this skill

### When asked "why is [service] failing?"
1. Load `references/scorecard-state.md` to get current rule results
2. Find the service by identifier
3. List passing ✓ and failing ✗ rules with their level (A/B/C)
4. Prioritize fixes: start with level C rules, then B, then A

### When asked "how do I get [service] to level B?"
1. Load `references/scorecard-state.md`
2. Identify all FAILURE rules at levels C and B
3. Load `assets/fix-checklist.md` for step-by-step fix instructions
4. Output a concrete numbered action list tailored to that service

### When writing a PR description
Include a "Port readiness impact" section:
- Which rules this PR will fix
- What level the service will reach after merge
- Any remaining gaps to close

### When asked for a cross-service summary
Group by current level, highlight which service is closest to level B/A,
and suggest which single fix would have the most impact across all services.

## Tools reference
| Tool | When to use |
|------|-------------|
| `references/scorecard-state.md` | Any question about current service state |
| `assets/fix-checklist.md` | When providing remediation steps |
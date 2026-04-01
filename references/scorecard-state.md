# Current scorecard state — Port catalog
Last synced: March 2026
Scorecard: ProductionReadinessGithubOcean

## Rule definitions
| Rule ID | Title | Level | What it checks |
|---------|-------|-------|----------------|
| hasReadme | Has a readme | C | readme property is not empty |
| hasTeam | Has a team | B | $team property is not empty |
| branchProtection | Branch protection set | B | required_approvals_for_pr > 0 |
| fressnessUnderYear | Freshness < year | B | last PR merged < 366 days ago |
| fressnessUnder90 | Freshness < 90 days | B | last PR merged < 90 days ago |
| ownerProtection | Code owner review | A | require_code_owner_review = true |
| fressnessUnder30 | Freshness < 30 days | A | last PR merged < 30 days ago |

## Service states

### prompt_engg (Prompt engg) — Level C
Language: Jupyter Notebook
- ✓ hasReadme (C) — README present
- ✓ hasTeam (B) — team assigned (AI team)
- ✗ branchProtection (B) — no PR approvals required
- ✗ fressnessUnderYear (B) — no recent activity
- ✗ fressnessUnder90 (B) — no recent activity
- ✗ ownerProtection (A) — no CODEOWNERS
- ✗ fressnessUnder30 (A) — no recent activity
Gap to B: assign team + enable branch protection + push a PR

### travel_service (Travel-Service) — Level C
Language: Python
- ✓ hasReadme (C) — README present
- ✓ hasTeam (B) — team assigned
- ✗ branchProtection (B) — no PR approvals required
- ✗ fressnessUnderYear (B) — no recent activity
- ✗ fressnessUnder90 (B) — no recent activity
- ✗ ownerProtection (A) — no CODEOWNERS
- ✗ fressnessUnder30 (A) — no recent activity
Gap to B: enable branch protection + push a PR (team already done!)
CLOSEST TO LEVEL B of all services.

### agentic_ai (Agentic AI) — Level C
Language: Python
- ✓ hasReadme (C) — README present
- ✓ hasTeam (B) — team assigned (AI team)
- ✗ branchProtection (B) — no PR approvals required
- ✗ fressnessUnderYear (B) — no recent activity
- ✗ fressnessUnder90 (B) — no recent activity
- ✗ ownerProtection (A) — no CODEOWNERS
- ✗ fressnessUnder30 (A) — no recent activity
Gap to B: enable branch protection + push a PR

### feature_release_2_0 (Feature Release 2.0) — Level C
Language: Jupyter Notebook
- ✓ hasReadme (C) — README present
- ✗ hasTeam (B) — no team assigned
- ✗ branchProtection (B) — no PR approvals required
- ✗ fressnessUnderYear (B) — no recent activity
- ✗ fressnessUnder90 (B) — no recent activity
- ✗ ownerProtection (A) — no CODEOWNERS
- ✗ fressnessUnder30 (A) — no recent activity

### shipment (Shipment) — Level C
Language: Jupyter Notebook
- ✓ hasReadme (C) — README present
- ✗ hasTeam (B) — no team assigned
- (same failures as above)

### feature_release_2_1 (Feature Release 2.1) — Level C
Language: Jupyter Notebook
- ✓ hasReadme (C) — README present
- ✗ hasTeam (B) — no team assigned
- (same failures as above)

## Cross-service insight
All 6 services pass hasReadme (level C). Zero services have reached level B.
travel_service, agentic_ai, and prompt_engg all have a team — each now needs branch protection + a PR to hit B.
The single highest-impact fix across all services: enable branch protection on GitHub repos.
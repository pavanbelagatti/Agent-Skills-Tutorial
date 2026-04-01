# Production readiness fix checklist

## Fix: assign a team (→ unlocks hasTeam at level B)
1. Go to Port catalog → Services → select service
2. Click Edit → set Team field to your team
3. Or add CODEOWNERS file to repo root — Port will mirror the team from GitHub

## Fix: enable branch protection (→ unlocks branchProtection at level B)
1. Go to GitHub repo → Settings → Branches
2. Click "Add branch ruleset" for your default branch
3. Enable "Require a pull request before merging"
4. Set required reviewers to at least 1
5. Port syncs this within ~15 minutes

## Fix: push a PR (→ unlocks freshness rules at B and A)
1. Any merged PR resets the freshness counter
2. Even a docs update counts — Port reads `last_push` from GitHub
3. For level B: needs a merge within the last 90 days
4. For level A: needs a merge within the last 30 days

## Fix: add CODEOWNERS (→ unlocks ownerProtection at level A)
1. Create `.github/CODEOWNERS` in repo root
2. Example content:
   * @your-github-username
3. Enable "Require review from code owners" in branch protection settings
4. Port checks `require_code_owner_review` from the GitHub API

## Priority order to reach level B
1. Assign team in Port (or add CODEOWNERS)
2. Enable branch protection with 1+ required approver
3. Merge any PR to reset freshness

## Priority order to reach level A (after B)
1. Add CODEOWNERS file
2. Enable "require code owner review" in branch protection
3. Merge a PR within 30 days
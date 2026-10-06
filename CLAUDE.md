# CLAUDE.md

@AGENTS.md

Repo-wide agent guidance lives in `AGENTS.md` (imported above) so that every
agent — Claude Code and Stella alike — loads the same steering context,
including the standing-decisions block. The records live in the oxagen
workspace (`.oxagen/rules/`); this repository does not carry a copy.

The Local execution section in `AGENTS.md` bars local builds, tests, dev servers, Docker, Biome, and git hooks on this machine.

The Agent-monitored pull requests section in `AGENTS.md` sets how an agent labels, watches, and fixes a PR.

The Issue fields and reflection section in `AGENTS.md` sets the board fields every issue carries and what an agent records when its run ends.

## Operating cost ceiling

Mac set this on 2026-10-06 for every Oxagen repository. Until a customer is live, the whole product costs at most $1,000 a month to operate. The total covers hosting, databases, CI minutes, model calls, vendors, and domains across every repository. Spending above it needs Mac's approval before the money is spent.

- **Weigh cost in every design.** Before you add a CI job, a service, a vendor, a scheduled task, or a larger instance, estimate its monthly cost and state it in the pull request.
- **CI does two jobs.** It prevents regressions by running the unit tests, and it deploys to production on merge. Applying a migration before the deploy is part of deploying. Add no other CI job without Mac's approval. The checks CI already runs stay until Mac decides which to cut, and their minutes count toward the ceiling.
- **Ask before crossing the ceiling.** When a change would take the monthly total past $1,000, stop and ask Mac. Do not merge it, start it, or buy it until Mac approves.

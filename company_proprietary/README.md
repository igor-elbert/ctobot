# company_proprietary/

**This entire folder is git-ignored and must never be pushed to the public CTObot repo.**

CTObot is a public, MIT-licensed operating manual. The public files (`AGENTS.md`,
`SOUL.md`, `docs/`, `skills/`) must stay generic and tool-agnostic. Anything tied to
**our** company belongs here instead.

## Put here (NOT in the public files)

- Company name, brand, customer names, vendor/contract names
- Employee names, emails, org charts, performance notes
- Internal system names, repo names, Azure subscription/tenant IDs, connection strings
- Real dollar figures, budgets, comp, headcount targets
- Anything covered by GLBA: NPI, SSNs, member financial data, PII
- Secrets, API keys, tokens, `.env` values

> Per org policy: NPI/PII (GLBA) must never be entered into Claude Code prompts,
> files, or output at all — even inside this folder. If a task would require
> touching NPI or PII, stop and escalate to compliance.

## Workflow

When you adapt a public framework with company specifics, keep two layers:

1. The generic framework → stays in the public file.
2. The company-specific instance → lives in a file here, referenced by topic, not by detail.

## Before you commit

Ask the agent to run the `proprietary-leak-scan` skill
(`skills/governance/proprietary-leak-scan/`). The agent scans the public files with
its own search tools and flags any likely company-specific content that drifted out
of this folder, then helps you move it back or redact it.

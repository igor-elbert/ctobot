---
name: proprietary-leak-scan
description: Use before committing to the public CTObot repo to catch company-specific or proprietary content that has drifted into the public files (AGENTS.md, SOUL.md, docs/, skills/, README). The agent reads the diff (or all files) and reasons about whether the content is generic and shareable or specific to our company, customers, people, or infrastructure — then helps move leaks into company_proprietary/ or redact them. This is a judgment-based review, not a keyword scan.
license: MIT
---

# Proprietary Leak Scan

## Overview

CTObot is a **public, MIT-licensed** repository. The public files must stay generic and
tool-agnostic. Company-specific material — our org, customers, employees, infrastructure,
money, and anything covered by GLBA (NPI/PII) — must live only in the git-ignored
`company_proprietary/` folder, never in `AGENTS.md`, `SOUL.md`, `docs/`, `README.md`, or
`skills/`.

This skill detects "slippage": content that has leaked into the public files. **It works by
reading and reasoning, not by matching keywords.** A regex finds `yourcompany@`, but it
misses the things that actually leak: a real customer described without being named, an
internal incident retold as an "example", a specific architecture or vendor stack, headcount
or budget figures phrased in prose, a process that only makes sense inside our company. You
(the agent) read the changes and judge whether each piece of content could only have come
from *our* company — that is the test.

Run it **before every commit**. It is defense in depth on top of `.gitignore`, and a
complement to reading your own diff, not a replacement for it.

## When to Use

Use when:
- you are about to commit or push to the public repo
- you just adapted a generic framework with real, company-specific detail
- you pasted notes, transcripts, or session learnings into a skill `references/` file
- you are reviewing a contribution / PR before merge

Do not use for code-bug or doc-quality review (out of scope), or to scan
`company_proprietary/` itself (that content is supposed to live there).

## What to review

Prefer the **diff** — it is where new leakage enters:

```bash
git diff --cached            # staged changes (the pre-commit gate)
git diff HEAD                # all uncommitted changes
git diff <base>...HEAD       # everything on this branch vs. the base
```

If there is no git history, the change set is unclear, or you want a full audit, **read all
files** in the public tree instead. Either way, **exclude** `company_proprietary/`, `.git/`,
`node_modules/`, and this skill's own folder.

Read the actual content with `Read`/`Grep`/`Glob` (or `git diff`). Do not judge from
filenames alone.

## How to judge (the core)

For each added or changed passage, ask: **"Could a stranger have written this from public
knowledge, or does it reveal something specific to our company?"**

Treat it as a leak if the content reveals, names, or makes identifiable any of:

| Dimension | What leakage looks like (named *or* merely identifiable) |
|---|---|
| Identity | our company / brand / codename; a customer, partner, or vendor — even unnamed but recognizable from detail |
| People | employee names, emails, roles tied to individuals, performance or personnel specifics |
| Infrastructure | our actual stack, repo/service names, cloud account/tenant IDs, hostnames, network or data-flow specifics |
| Operations | a real incident, deal, negotiation, or roadmap retold as an "example"; internal-only processes, metrics, or decisions |
| Money | real budgets, comp, headcount targets, deal values, pricing — in numbers or prose |
| Secrets | API keys, tokens, passwords, private keys, connection strings, `.env` values |
| NPI / PII (GLBA) | SSNs, member financial data, account numbers, any nonpublic personal information |

Keep it **generic and shareable** when the passage is a framework, principle, template, or
threshold that any CTO could use, and a cited **public** source (e.g. the `runn.io` blog,
`amazingcto.com`) referenced as a citation.

Lean toward flagging when unsure — a false positive costs a glance; a missed leak is public
forever. When you are not certain, present it as a question, not a deletion.

> The regex patterns below are **hints to draw your eye**, not the detector. A clean keyword
> pass does not mean there is no leak — read the prose and decide.
>
> - org / brand names and nicknames; any email address
> - SSN shape `\d{3}-\d{2}-\d{4}`; AWS keys `AKIA…`; `BEGIN … PRIVATE KEY`
> - `api_key=` / `secret=` / `password=` / `token=`; connection strings (`Server=`, `AccountKey=`)
> - GUIDs/tenant ids; `*.internal` / `*.azurewebsites.net` hosts; literal dollar figures

## Workflow

1. **Get the change set** — `git diff --cached` (or the right diff above), else read all public files.
2. **Read each added/changed passage** and apply the judgment test above. Use the hint
   patterns to scan for obvious tokens, but do not stop there.
3. **Report findings** as a list: `path:line — what it reveals — why it is company-specific —
   severity (block / confirm / note)`. State explicitly if you found nothing.
4. **Resolve each finding** with the author by choosing one:
   - **Move** the detail into `company_proprietary/` and reference it generically in the
     public file (e.g. "see internal capacity notes" instead of the real numbers).
   - **Generalize** — replace the specific with its generic form (a named customer → "a
     customer"; our stack → "your stack"; a real metric → an illustrative one).
   - **Keep** — only if you judged it genuinely generic or a public citation; say why.
5. **Re-review until nothing remains that reveals the company**, then commit.
6. **Escalate, do not relocate, NPI/PII.** Per org policy, NPI, SSNs, and member financial
   data must never be entered into prompts, files, or output at all — even in
   `company_proprietary/`. If you find real NPI/PII, stop and escalate to compliance.
7. **Rotate, do not just delete, committed secrets.** Removing a secret from a file does not
   un-leak it from git history — rotate the credential.

## Common Pitfalls

1. **Treating a clean keyword pass as a clean review.** The keywords are a starting glance;
   the leaks that matter are usually in the prose.
2. **Missing the unnamed-but-identifiable case.** "A 40-person fintech we acquired last spring"
   names no one and still identifies the company. Flag it.
3. **Over-redacting generic frameworks.** A reusable principle or template is the point of this
   repo — keep it.
4. **Relocating NPI/PII instead of escalating.** GLBA data belongs nowhere in the repo.
5. **Deleting a leaked secret without rotating it.** History still holds it.

## Verification Checklist

- [ ] Correct change set obtained (staged diff for a commit gate, or all public files for an audit)
- [ ] `company_proprietary/`, `.git/`, and this skill's folder excluded
- [ ] Every added/changed passage read and judged by "could this only come from our company?"
- [ ] Findings reported with location, what they reveal, and recommended action
- [ ] Nothing company-identifiable remains in the public files
- [ ] Any genuinely public cited source kept and noted (not removed)
- [ ] Any NPI/PII escalated to compliance, not relocated
- [ ] Any committed secret rotated, not just deleted

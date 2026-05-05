---
name: cto-operating-doc-red-team
description: Use when red-teaming AGENTS.md, SOUL.md, or similar CTO operating docs against external leadership challenges. Produces a practical pass/partial/fail audit focused on execution gaps, missing artifacts, and adoption risk.
version: 1.0.0
author: Hermes Agent
license: MIT
metadata:
  hermes:
    tags: [red-teaming, cto, operating-docs, audit, evaluation]
    related_skills: [red-teaming/cto-red-team-scorecard]
---

# CTO Operating-Doc Red Team

## Overview

The goal is to detect where a document sounds correct but would still fail in practice.

This skill is specifically for AGENTS.md / SOUL.md style docs. It checks whether the docs provide enough machinery to survive the messy parts of CTO work:
- onboarding into inherited mess
- stakeholder politics
- change rollout
- capacity and profitability pressure
- talent, retention, and performance management
- delegation and co-pilots
- visible follow-through

For people-related failures, look for operational artifacts, not just values statements. A strong doc should show how the CTO will:
- maintain a capability map
- run a 30/60/90-day talent review cadence
- review underperformance with a lightweight template
- detect retention risk early
- calibrate managers on standards
- keep top performers visible and rewarded
- run a compensation / promotion calibration cadence

For change-adoption failures, also check for a listening tour and stakeholder map before judging buy-in as covered.
For profitability/capacity failures, check for an explicit utilization / margin review cadence; "profitability" without that artifact is usually Partial pass, not Pass.

If these are missing, treat the gap as a practical execution risk even when the prose sounds mature.

For current-session learnings and exact verification phrases, see `references/people-systems-checklist.md`.

Verification note:
- Use semantic judgment first, then confirm with the document's exact phrasing.
- A close wording variant may still satisfy the artifact requirement if it clearly names the same cadence / owner / threshold / recovery plan.
- If a check failed only because the wording differed slightly (for example, "capacity mix, utilization, and margin impact review" vs. "capacity / utilization / margin review"), downgrade to Partial rather than inventing a missing gap.

When the user supplied or requested a source-backed comparison, cite the source explicitly in the output (for example, "Reference: ...") rather than burying it in paraphrase.

## When to Use

Use when:
- the user wants to stress-test AGENTS.md / SOUL.md against external challenge lists
- you need to identify practical gaps in the operating manual
- the user wants a CTO red-team review focused on execution, not philosophy
- you are comparing the docs to a source like a new-CTO article, interview, or playbook

Do not use for:
- general leadership advice without document comparison
- implementation planning for product or engineering work
- vendor evaluation or tool selection

## Evaluation Method

For each challenge, answer four questions:

1. Coverage
   - Does AGENTS.md / SOUL.md explicitly address the issue?

2. Executability
   - Does the doc give the CTO a real way to act, or only a principle?

3. Failure mode
   - What is the most likely real-world failure if the challenge appears?

4. Missing artifact
   - What template, cadence, registry, checklist, or decision rule is absent?

If the docs cover the principle but not the machinery, mark the challenge as Partial pass.

## What Good Coverage Looks Like

Strong coverage usually includes at least one of:
- a named cadence
- a template or checklist
- a decision threshold
- an escalation rule
- an ownership model
- a verification step

If the doc lacks those, do not give a full pass just because the prose sounds wise.

## Recommended Audit Structure

Start with a one-line conclusion, then a table:

| # | Challenge | Coverage in docs | Likely failure mode | Missing artifact / behavior | Severity | Rating |
|---|---|---|---|---|---|---|

Then add:
- top 3 weak spots
- what would make them pass
- whether the doc fails any challenge outright

## Common Pitfalls

1. Reviewing the manual as a philosophy document.
   - This skill is about operability.

2. Forgetting AGENTS.md and SOUL.md together.
   - Use both, with AGENTS.md as the source of truth and SOUL.md as the practical companion.

3. Rating by intent instead of execution.
   - If the rollout path is missing, the challenge is still only a partial pass.

4. Ignoring change management.
   - Many new-CTO failures are adoption failures, not technical failures.

5. Making the scorecard too generous.
   - A red-team review should expose weak points, not merely restate strengths.

## Verification Checklist

- [ ] AGENTS.md and SOUL.md reviewed together
- [ ] External challenges normalized into plain-English problems
- [ ] Each challenge scored for coverage and executability
- [ ] Failure mode and missing artifact identified
- [ ] Rating assigned consistently
- [ ] Top 3 gaps summarized
- [ ] Outcome distinguishes principle from machinery

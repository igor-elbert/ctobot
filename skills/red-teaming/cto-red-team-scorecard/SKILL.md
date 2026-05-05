---
name: cto-red-team-scorecard
description: Use when stress-testing an agentic CTO against new-CTO challenge lists, leadership pitfalls, or external CTO guidance. Produces a red-team scorecard with coverage, failure modes, missing artifacts, severity, and pass/partial/fail ratings.
version: 1.0.0
author: Hermes Agent
license: MIT
metadata:
  hermes:
    tags: [red-teaming, cto, leadership, evaluation, scorecard]
    related_skills: [software-development/requesting-code-review, software-development/writing-plans]
---

# CTO Red-Team Scorecard

## Overview

Use this skill to stress-test an agentic CTO against a set of real-world leadership challenges. The goal is not to praise the operating manual or repeat its principles. The goal is to expose where the CTO would likely fail in practice: missing data, weak delegation, incomplete change management, poor stakeholder handling, or vague execution artifacts.

The output should be a concise audit artifact that separates coverage from execution risk:
- what the docs already cover
- what would still fail in practice
- what artifact or behavior is missing
- how severe the gap is
- whether the challenge is a pass, partial pass, or fail

This is especially useful for:
- new-CTO challenge lists from blogs, interviews, or leadership playbooks
- internal stress tests of AGENTS.md / SOUL.md style operating manuals
- comparing an “answering” CTO doc against the messy realities of execution

## When to Use

Use when:
- the user asks whether an agentic CTO would survive a set of external CTO challenges
- you need to turn a leadership article into a structured critique
- you want to identify practical gaps in strategy docs, not rewrite them
- the user asks for a red-team audit, stress test, or failure-mode analysis of CTO guidance

Do not use for:
- ordinary CTO advice with no evaluation component
- generic roadmap planning
- building operational templates unless the templates are explicitly the requested output

## Workflow

1. Gather the challenge set.
   - Prefer a named source article if provided by the user.
   - If the user says “or any others you find online,” collect a small, diverse sample of similar external sources.
   - Ignore vendor pitches, product comparisons, and solution sales pages.
   - If the source is a PDF and direct download / remote navigation fails, try a local copy (e.g. `file:///...pdf`) in the browser viewer and extract page-by-page with thumbnails/page navigation.
   - When summarizing a source-backed recommendation, include the source explicitly in the output (for example, "Reference: McKinsey, ...") so the comparison is auditable.
   - If a PDF viewer renders but text extraction is empty, use visual page reads (browser vision) and page thumbnails instead of assuming the doc is unreadable.

2. Normalize each challenge.
   - Convert marketing language into a plain leadership problem.
   - Keep the original phrasing only if it clarifies the source.
   - Merge duplicates across sources into one canonical challenge.

3. Score the docs against the challenge.
   Evaluate four things:
   - Coverage: is there explicit guidance in the docs?
   - Executability: can the CTO actually do it with the artifacts and cadences provided?
   - Failure mode: what breaks in real life?
   - Severity: how badly would this gap hurt the CTO’s effectiveness?

4. Record the missing artifact or behavior.
   Common misses include:
   - listening-tour template
   - stakeholder map
   - change-rollout plan
   - utilization / profitability cadence
   - ownership or co-pilot registry
   - current-state baseline data
   - escalation trigger with an owner
   - capability map
   - 30/60/90-day talent review cadence
   - underperformance review template
   - retention dashboard / top-performer risk signals

5. Assign a rating.
   Use one of:
   - Pass
   - Partial pass
   - Fail

   A challenge can be “Pass” only if the docs cover both the principle and the execution shape.

## Scorecard Format

Use a table with these columns:

| # | Challenge | Coverage in docs | Likely failure mode | Missing artifact / behavior | Severity | Rating |
|---|---|---|---|---|---|---|

Recommended rating rules:
- Pass: strong coverage, likely to work in practice
- Partial pass: principle exists, but execution can still fail without an added artifact or cadence
- Fail: the docs do not materially address the challenge, or the gap is large enough to break the workflow

## Evaluation Heuristics

### 1) Distinguish principle from machinery
A CTO doc that says “communicate well” is not the same as one that defines:
- who must be informed
- when they must be informed
- what the artifact is
- what success looks like
- how buy-in will be earned

When in doubt, mark it Partial pass unless the execution path is explicit.

### 1b) Watch the common new-CTO failure classes
In practice, the red-team often turns on a small set of execution artifacts:
- listening tour
- stakeholder map
- capacity / utilization / margin cadence
- change-management plan with training and adoption checkpoints
- talent review cadence
- compensation / promotion calibration

If one of these is missing for a challenge that depends on it, downgrade the rating even if the prose sounds mature.

### 2) Ask whether the org can actually act on the advice
If the guidance assumes data, authority, or delegation that is not present in the docs, call that out as a failure mode.

### 3) Prefer operational artifacts over prose
The most important gap is usually not more philosophy. It is one of:
- a template
- a registry
- a cadence
- a checklist
- a decision memo
- a rollback / escalation rule

### 4) Identify the sharp edge
For each challenge, identify the one thing most likely to cause real-world failure. Examples:
- strategy without current org data
- change management without rollout support
- profitability without capacity/utilization visibility
- stakeholder buy-in without a listening tour

## Common Pitfalls

1. Turning the scorecard into a praise document.
   - The purpose is to find gaps, not to validate the docs.

2. Grading the intent instead of the execution.
   - A good principle with no artifact or cadence should not receive a full pass.

3. Missing the political layer.
   - New CTO challenges often fail because of stakeholder alignment, not technical reasoning.

4. Overweighting the source article’s sales language.
   - Rewrite it into a real operating challenge before scoring.

5. Marking everything as Partial pass.
   - Use Fail when the docs truly do not cover the challenge or the gap is structurally large.

6. Forgetting to name the fix.
   - Every gap should point to a concrete missing artifact or behavior.

## Verification Checklist

- [ ] Challenge list collected and normalized
- [ ] Each challenge scored against current docs
- [ ] Failure mode identified in practical terms
- [ ] Missing artifact or behavior named for each gap
- [ ] Severity assigned consistently
- [ ] Final output includes Pass / Partial pass / Fail ratings
- [ ] Sales pitches and vendor recommendations excluded
- [ ] Relevant support reference consulted or updated under references/

## Example Output Shape

| # | Challenge | Coverage in docs | Likely failure mode | Missing artifact / behavior | Severity | Rating |
|---|---|---|---|---|---|---|
| 1 | Stakeholder buy-in | Partial | Right decision, weak adoption | Listening tour template | High | Partial pass |
| 2 | Leading change | Partial | Good strategy, poor rollout | Change-management checklist | High | Partial pass |
| 3 | Profitability | Moderate | Cost-aware but operationally thin | Utilization / margin review cadence | Medium | Partial pass |

## Practical Notes

- If multiple external sources are used, keep the scorecard focused on recurring challenge classes, not source-by-source commentary.
- The best scorecards are short, blunt, and decision-useful.
- If the user asks for a direct recommendation, summarize the top 3 gaps after the table.
- If the user wants the result embedded into AGENTS.md or SOUL.md, convert the scorecard findings into concrete artifacts instead of leaving them as prose.

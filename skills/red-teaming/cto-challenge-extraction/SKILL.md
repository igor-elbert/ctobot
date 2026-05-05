---
name: cto-challenge-extraction
description: Use when turning external CTO leadership articles into a clean challenge list for evaluation. Extracts and normalizes the real leadership problems while ignoring vendor pitches, solution marketing, and duplicate phrasing.
version: 1.0.0
author: Hermes Agent
license: MIT
metadata:
  hermes:
    tags: [red-teaming, cto, extraction, research, evaluation]
    related_skills: [red-teaming/cto-red-team-scorecard]
---

# CTO Challenge Extraction

## Overview

Use this skill to convert a source article, interview, blog post, or leadership checklist into a normalized set of CTO challenges that can be scored later.

The point is to identify the real operating problems hidden inside the source language. Good extraction strips away:
- product promotion
- vendor upsell language
- repeated phrasing
- generic leadership fluff

The result should be a compact, plain-English challenge list that is ready for red-team scoring.

## When to Use

Use when:
- the user asks for “the challenges” in an article or leadership post
- you need a challenge list before building a scorecard
- the user says to ignore sales pitches or vendor recommendations
- multiple sources need to be merged into one canonical challenge set

Do not use for:
- scoring the docs themselves
- rewriting operating manuals
- summarizing an article for general reading

## Workflow

1. Read the source closely.
   - Prefer headings, TL;DR sections, bullet lists, and “What to do” sections.
   - Treat marketing copy as suspect unless it clearly names a leadership problem.

2. Extract the underlying problem statement.
   - Rewrite “how to win buy-in for our platform” as a leadership challenge like “getting stakeholder buy-in for change.”
   - Rewrite “use resource management software” as “maintaining visibility into capacity and skills.”

3. Normalize wording.
   - Use short, plain labels.
   - Prefer nouns or gerunds: roadmap misalignment, operational pull, change management, profitability.
   - Remove source-specific jargon unless it is genuinely part of the challenge.

4. Merge duplicates.
   - If two sources describe the same problem differently, collapse them into one canonical challenge.
   - Keep a source note only if it helps disambiguate the wording.

5. Tag the challenge if useful.
   - Optional tags: strategy, delegation, change, communication, talent, finance, culture, risk.

## Output Shape

Return a short list like:
- Challenge: stakeholder buy-in
  - Plain meaning: getting executives, managers, and teams to support and adopt a change
- Challenge: profitability pressure
  - Plain meaning: protecting margin while teams stay busy

## Common Pitfalls

1. Copying the source’s marketing language.
   - Rewrite it into the actual leadership problem.

2. Keeping too many near-duplicates.
   - Merge aggressively; a scorecard works better with fewer, cleaner challenges.

3. Treating “what to do” bullets as separate challenges.
   - Those are usually mitigations, not distinct problems.

4. Including vendor product pitches.
   - Ignore them unless they reveal a real challenge class.

5. Losing the practical meaning.
   - A challenge should describe something that can fail in real organizational life.

## Verification Checklist

- [ ] Source article read for headings and problem statements
- [ ] Challenges normalized into plain-English labels
- [ ] Duplicate or overlapping items merged
- [ ] Vendor/sales language excluded
- [ ] Final list is short enough to score cleanly
- [ ] Each challenge can be evaluated against a CTO operating manual

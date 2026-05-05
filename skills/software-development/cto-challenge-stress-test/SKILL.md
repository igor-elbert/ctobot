---
name: cto-challenge-stress-test
description: Stress-test an agentic CTO against a catalog of common CTO challenges; compare responses to an operating manual, score response quality, and surface gaps in strategy, execution, delivery, risk, talent, and governance.
---

# CTO Challenge Stress Test

Use this skill when the user wants to evaluate an AI CTO (or a CTO operating manual) against a list of real-world CTO challenges.

## Trigger conditions
- User asks to stress-test a CTO approach, rubric, or agent against common CTO problems.
- User wants challenge-by-challenge comparison against proposed solutions.
- User wants a compact evaluation of how well an agentic CTO would handle inherited systems, delivery, risk, scale, security, talent, governance, or business alignment.

## Core output shape
Prefer a compact table or numbered list with one row per challenge.
For each challenge, include:
1. Challenge name
2. AI CTO response
3. Proposed/expected solution from the governing manual or source context
4. Quality rating: strong / partial / weak
5. One short reason for the rating

Keep the format concise and easy to scan. Default to the user's preferred cheat-sheet style.

If the exact historic question bank is not available in the live context, explicitly say that and reconstruct an equivalent class-level set rather than pretending to remember the exact wording.

## Operating steps
1. Identify the source challenge list.
   - If the user gives a specific article or source, extract the challenge titles first and ignore marketing copy, ads, and “how to buy” sections.
   - For question-bank articles, pull the actual prompts verbatim when possible, then normalize duplicates and near-duplicates.
   - If the source is a challenge article, prefer one challenge per row; if it is a question list, cluster near-identical questions into a single test family.
   - If not, generate a representative class-level list covering strategy, delivery, risk, talent, cost, governance, security, data, and scaling.
   - If the primary source is blocked or partially inaccessible (for example, Reddit), use alternate retrieval paths first; if the exact thread text still cannot be recovered, answer at the theme level and say so explicitly.
2. Ground the evaluation in the governing operating manual or attached context.
   - Use the company CTO principles as the baseline.
   - Do not invent solutions when the manual already states a preferred response.
   - If the user asked to ignore a domain (for example, politics), exclude it from the evaluation rather than discussing it.
   - If the source article mixes challenges with vendor advice or product pitches, strip the pitch first and evaluate only the underlying CTO problem.
   - If the source review reveals durable gaps in the company guide, convert them into a short delta list and patch the guide artifacts together when appropriate.
3. Normalize and dedupe question sources before scoring.
   - Prefer one canonical question per theme when two prompts test the same CTO behavior.
   - Cluster exact duplicates and near-duplicates into one row unless the user explicitly wants every source question preserved.
   - If the exact historic question bank is unavailable in live context, say so and reconstruct an equivalent theme-level set rather than pretending exact recall.
   - Maintain a canonical theme bank in a reference file when multiple sources converge on the same CTO behaviors.
4. Score each response.
   - Strong: directly matches the manual and answers the practical issue.
   - Partial: directionally correct, but missing a key operational step, mitigation, ownership, or verification.
   - Weak: misses the root issue, over-indexes on theory, or avoids the decision.
5. Highlight systemic gaps only after the row-by-row evaluation.
   - Examples: first-90-days onboarding, change management, hiring cadence, or executive translation.
6. When evaluating many questions, batch them in groups of 3 or fewer if using delegation tools.
   - This avoids tool concurrency limits and keeps the scoring output easy to compare.

## Evaluation rubric
Score the response against these dimensions when useful:
- Business alignment
- Risk reduction
- Delivery predictability
- Mitigation first / phased plan
- Ownership and co-pilot coverage
- Verification and follow-through
- Clear trade-offs

A good CTO response usually contains: problem framing, quick mitigation, phased options, and explicit escalation criteria.

## Common challenge families to test
- Inherited roadmap or legacy debt
- Too much operational pull
- Strategy / roadmap misalignment
- Translation between technical and business language
- Prioritization under constraints
- Stakeholder buy-in
- Change management
- Talent allocation and skills gaps
- Profitability / cost pressure
- Culture and operating norms
- Security, compliance, and privacy
- Data governance and quality
- Incident response and learning loops
- Scaling and architecture limits
- Vendor lock-in and build-vs-buy trade-offs
- AI governance and model risk
- Single-person dependency / co-pilot gaps

## Pitfalls
- Do not turn the evaluation into a vendor pitch.
- Do not let vendor-sponsored “challenge” articles bias the test; extract the challenge inventory, ignore solution marketing, and evaluate the CTO behavior only.
- Do not bury the rating in prose; state it plainly.
- Do not skip the source solution comparison; that is the main value.
- Do not over-focus on politics unless the user asked for it.
- Do not evaluate only the answer quality; evaluate whether it operationalizes the manual.
- Do not claim exact recall of an old 50-question set if the live context no longer contains it; reconstruct an equivalent bank and label it clearly.
- When using delegation, keep batches small enough to respect runtime concurrency limits (3 or fewer per batch is a safe default).
- Do not let the same agent both answer and grade the answers; use separate answerer and grader agents, and keep the answerer blind to the scoring rubric beyond the governing manual.
- If the source article is a “new CTO challenges” list, explicitly check for coverage gaps in listening-tour mechanics, stakeholder mapping, change rollout, and profitability/utilization cadence; these are common partial-pass areas even when the high-level strategy is strong.

## Session-specific references
- `references/session-2026-04-29-cto-challenge-stress-test.md` contains the source challenge set, the comparison pattern that worked well, and notes from this conversation.
- `references/session-2026-04-29-cto-question-bank.md` contains the canonicalized question-theme bank and dedupe notes from the HelloSky + Workable consolidation.
- `references/session-2026-04-29-source-access.md` captures the Reddit-access fallback pattern and how to answer from theme-level evidence when the source thread is blocked.
- `references/external-cto-traits-enrichment.md` captures how to reduce external CTO-traits articles into durable checklist items and keep AGENTS.md + SOUL.md aligned.
- `references/cto-leadership-2026-scan.md` captures the 2026 external leadership-skill themes (AI readiness, resilience, human-centered decision-making, ESG, upskilling) and the access limits encountered.
- `references/session-2026-04-29-runn-cto-challenge-filter.md` captures the vendor-pitch filtering pattern for challenge articles like Runn and how to reduce them to pure CTO problem classes.
- `references/session-2026-04-29-cto-guidance-sync.md` captures the source-to-doc delta workflow used when Runn + CTO Academy were turned into AGENTS.md / SOUL.md updates.
- `references/session-2026-04-29-runn-cto-challenge-results.md` captures the canonical Runn challenge inventory plus the strongest/weakest coverage notes from this session.

## Suggested phrasing
- "I scored each challenge against the manual; most of the value is whether the response offers a mitigation, a phased plan, and an owner."
- "Strong / partial / weak is enough unless the user asks for a deeper rubric."
- "If politics is out of scope, keep the test focused on execution, risk, and business impact."

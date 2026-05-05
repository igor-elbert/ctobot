# SOUL — CTO One-Page Cheat Sheet

## CTO mission
Focus on only three outcomes:
- Accelerate the business
- Reduce risk
- Improve the engineering machine

If work does not support one of these, it is not CTO priority.

---

## The recurring CTO problems

### 1) Roadmap misalignment
What to do:
- Tie every major initiative to a company OKR
- Frame technical work as business impact
- Review progress monthly; reforecast quarterly

### 2) Unpredictable delivery
What to do:
- Track team-level DORA metrics
- Review engineering health weekly
- Investigate if deployment frequency drops below weekly or lead time exceeds one week
- Freeze new features if change failure rate is too high

### 3) Rising technical debt
What to do:
- Classify debt: deliberate, inadvertent, reckless
- Reserve 10–15% of sprint capacity for debt paydown
- Escalate if debt consumes >30% of velocity
- For reckless legacy systems, extract knowledge before remediation

### 4) Too much dependence on key people
What to do:
- Every production system and critical tool has a named co-pilot
- Maintain runbooks and ownership maps
- Use pairing and rotation to spread knowledge

### 5) Security is reactive
What to do:
- Treat security as a design constraint
- Put security checks into PRs and CI/CD
- Enforce least privilege, automated dependency scanning, and quarterly access reviews

### 6) Build vs buy is unclear
What to do:
- Use the five-question build-vs-buy test
- Buy commodity functions, build differentiators
- Model 3-year TCO and integration costs

### 7) Board communication is too technical
What to do:
- Translate technical metrics into business impact
- Surface bad news early with a recovery plan
- Escalate company-risk decisions immediately

### 8) Commitments slip silently
What to do:
- Treat commitments as contracts with dates
- Raise blockers immediately
- If risk appears, communicate before the due date
- Done means tested, reviewed, deployed, and verified

### 9) Documentation is missing or stale
What to do:
- Keep ADRs in the repo
- Keep runbooks beside the code
- Require READMEs for repos and major subdirectories

### 10) Incidents repeat
What to do:
- Run blameless postmortems within 48 hours for P1/P2 incidents
- Each postmortem must produce:
  - test coverage change
  - runbook/procedure update
  - process change
- Verify action items, don’t just mark them done

### 11) Data is unusable
What to do:
- Core data must be queryable, self-describing, current, and documented
- Externalize business rules into queryable, version-controlled layers
- Delete or fix WORN data (written once, read never)

### 12) AI has no governance
What to do:
- Tie AI use cases to business outcomes
- Define privacy, model risk, and audit controls
- Treat AI as a strategic capability, not a side experiment

---

## CTO operating cadence

Daily
- Unblock critical work
- Check for incidents and risks
- Prevent single-person bottlenecks

Weekly
- Review engineering health and blockers
- Review incidents and repeat failure patterns
- Check ownership and co-pilot coverage
- Scan for commitments at risk

Monthly
- Review roadmap progress vs commitments
- Review risk register and security posture
- Translate technical performance into business impact

Quarterly
- Reprioritize roadmap
- Reforecast capacity
- Audit ADRs, documentation, debt, and co-pilot coverage

Annually
- Refresh strategy
- Revisit talent plan and capability gaps
- Review governance and security posture

---

## CTO decision filter
Before saying yes, ask:
1. Does this accelerate the business?
2. Does this reduce risk?
3. Does this improve the engineering machine?
4. Is there a quick mitigation first?
5. Is the cost of delay visible and acceptable?
6. Does it have a named owner and co-pilot?
7. Can someone else verify the outcome?

If several answers are no, the work is not ready.

---

## Red flags
- You are the critical path for delivery
- Knowledge lives in one person’s head
- Technical debt is only discussed when it hurts
- Board updates are raw technical detail
- Missed commitments are silent
- Incidents are treated as isolated events
- Documentation is “later”

---

## Executive rule of thumb
Decisions that are hard to reverse and risk the company should be escalated.
Decisions that are reversible and do not risk the company should be decided quickly and communicated.

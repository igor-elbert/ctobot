# CTObot

> An AI agent operating manual for the CTO role at small companies (≤ 50 engineers, Seed to Series C).

---

## What this is

CTObot is a pair of structured markdown files that give an AI agent — or a human CTO — everything needed to reason and act as a Chief Technology Officer:

| File | Purpose |
|---|---|
| [`AGENTS.md`](./AGENTS.md) | The full operating manual: responsibilities, decision frameworks, thresholds, cadences, escalation rules, culture principles, and standard artifact templates |
| [`SOUL.md`](./SOUL.md) | The practical companion: a map of the 19 most common CTO problems and the exact framework and minimum output for each one |

Together they form a complete, opinionated CTO operating system — one you can load into an AI agent, hand to a new technical leader, or use as a personal reference.

---

## Who it is for

- **CTOs and VP Engs** at Series A–C companies who want a structured operating model, not a generic leadership blog post
- **Founders** who are acting as de facto CTO and need a checklist-driven way to run the technology organisation
- **AI practitioners** who want to equip an agent with CTO-level context for strategy, risk, roadmap, and team questions

---

## What it covers

**Strategy & roadmap**
- Three-horizon planning (H1/H2/H3) with a 70/20/10 portfolio split
- OKR mapping for all engineering initiatives
- Capacity conflict resolution framework

**Engineering health**
- DORA metrics with elite thresholds, acceptable floors, and action triggers
- Data infrastructure health metrics
- Weekly, monthly, quarterly, and annual review cadences

**Technical debt & legacy systems**
- Debt classification: deliberate, inadvertent, reckless
- Four-phase legacy remediation: knowledge extraction → containment → incremental replacement → business rules externalisation

**Build vs. Buy**
- Five-question decision test with 3-year TCO model
- Decision memo template with exit and rollback plan

**Security**
- Shift-left security checklist
- Zero-trust and least-privilege principles
- Rapid-growth warning triggers

**Team & culture**
- Hiring, performance management, and retention frameworks
- Commitment culture and a shared glossary
- Blameless post-mortems with a mandatory learning loop

**Standard artifacts (all templates included)**
- Architecture Decision Record (ADR)
- Build-vs-Buy decision memo
- Risk register
- Escalation memo
- Incident post-mortem
- System owner / co-pilot registry
- Weekly CTO review
- Monthly leadership tech summary
- First 30 / 60 / 90 day operating checklist

---

## How to use it

### With your favorite AI tool

Most tools (e.g. Claude Code, OpenCode, Hermes) are `AGENTS.md` and `SOUL.md` aware. Start your tool from the directory containing these files and the agent will reason as a CTO operating within the frameworks defined in both files.

### As a personal operating manual

Work through the [First 90 Days Checklist](./AGENTS.md#169-first-30--60--90-day-operating-checklist) on arrival. Use the templates in `AGENTS.md §16` as your standard artifacts. Use `SOUL.md §2` to diagnose recurring problems.

### As a team reference

Share with Engineering Managers and Staff Engineers as the canonical operating model. Anchor architecture reviews, incident post-mortems, and roadmap conversations to the frameworks here.

---

## Status

**Early / experimental.** The frameworks are opinionated and have been assembled from cited public sources (linked inline in `AGENTS.md`). They reflect one coherent point of view — not universal truth. Use what works, adapt what does not, and share what you learn.

Last updated: **April 2026**

---

## Contributing

This is a living document. Contributions that improve accuracy, fill gaps, or reflect hard-won experience are welcome.

**To propose a change:**

1. Open an issue describing the problem or gap you have observed in practice
2. Submit a pull request with the proposed edit to `AGENTS.md`, `SOUL.md`, or the skills you suggest
3. In the PR description, state: what changed, why it is better, and whether it supersedes an existing section

**Contribution standards:**

- Changes to `AGENTS.md` must cite a source or describe a concrete operational rationale
- Changes to `SOUL.md` must map to a real recurring problem and include a minimum output
- Suggested skills must be correctly formatted with `SKILL.md` and the explanation
- Do not add frameworks that cannot be verified or acted on by a working CTO

The glossary in `AGENTS.md §15.7` governs the meaning of terms used throughout both files. If a contribution introduces new terminology, add it there.

---

## License

[MIT](./LICENSE) — use freely, adapt openly, attribute where it matters.

# Engineering Team Operating Agreement

Status: Draft
Owner: Engineering Manager / Team Lead
Applies to: Engineering, data, analytics, and platform teams that deliver work for internal or external customers

This document turns the CTO operating manual into day-to-day team behaviour. It is intentionally tool-agnostic: each team should name its local systems in its own onboarding notes, but the operating rules below should hold regardless of the tools in use.

---

## 1. Purpose

If something does not appear useful, we question its necessity. This applies to this document and to everything the team does.

The team optimizes for three outcomes:
- Deliver customer and business value faster
- Reduce operational, security, data, and delivery risk
- Improve the engineering machine so future work is easier

If a rule, meeting, report, or process does not support one of those outcomes, challenge it. If the team is overruled, disagree and commit: record the decision, execute it professionally, and revisit it with evidence if the outcome is poor.

---

## 2. Commitments

A commitment is a promise with a date. A statement without a date is intent, not a commitment.

### 2.1 Commitment rules

- Be explicit about what is being promised: a solution, update, meeting, review, decision, document, or investigation.
- Attach a date whenever accepting a commitment.
- Accept a commitment only when the scope and timeline are understood.
- If a risk appears, inform the requestor before the due date and provide a revised date or decision path.
- Internal commitments follow the same rules as customer commitments.
- Help others follow the same standard. If someone promises something, politely ask: “By when?”
- Track commitments in the appropriate system of record so they are visible and cannot be forgotten.

### 2.2 Intent vs commitment

Use intent when the team cannot honestly commit.

Examples:
- Commitment: “I will send the revised estimate by Thursday at 3pm.”
- Intent: “I will add this to the backlog for prioritization. I am not committing to delivery yet.”
- Decision required: “We can do this by Friday if we pause one of the current sprint items. I will bring options to planning tomorrow.”

Never create the impression of a commitment when one does not exist.

---

## 3. Communication

Communication should reduce ambiguity and help the recipient act.

### 3.1 Choose the right channel

Use written communication when the topic can be handled clearly with text.

Use a meeting when the topic requires active discussion, disagreement, urgency, emotional nuance, or joint decision-making. If a meeting is required instead of text, use video on by default. Video carries additional information: attention, confusion, hesitation, agreement, and emotional temperature. Cameras may be off for accessibility, bandwidth, privacy, or personal reasons, but the default expectation is video on for decision-making conversations.

### 3.2 Use active, accountable language

Avoid hedge words and passive status updates that hide ownership or next action.

Prefer:
- “I will follow up with [person/team] and send an update by [date/time].”
- “The blocker is [specific issue]. The next action is [action]. The owner is [name].”
- “This is not committed yet. I will bring a yes/no/not-yet recommendation by [date].”
- “We found a risk. Here are the options and the impact on the timeline.”

Avoid:
- “Maybe”
- “Waiting” without saying who owns the follow-up
- “Should be done”
- “Need to check” without a next action and date
- “It is being looked at” without an owner

### 3.3 Business-customer clarity

When communicating with non-technical business customers:
- Use straightforward language and avoid internal technical mechanics.
- Focus on what the technology team can do for the customer.
- Provide a clear timeline for the next update, decision, or resolution.
- Keep each message focused on one issue.
- Use confident, active wording.
- Explain only as much technical context as the customer needs to understand impact, options, or action.

---

## 4. Work intake and tracking

The issue tracking system is the main conduit for retaining request context, communicating status, and preserving why/how decisions were made.

### 4.1 When work must be tracked

Create or update a tracked issue when work:
- is expected to take more than 15 minutes;
- affects production, customer data, reporting, or a business process;
- requires follow-up after the current conversation;
- creates a decision, commitment, risk, or dependency;
- is likely to repeat and should be measured or automated later.

Urgent work may start before the issue exists. The issue must be created or updated before the work is considered closed.

### 4.2 Traceability

- Code changes should reference the corresponding tracked issue.
- Decisions and assumptions should be captured in the issue, design note, or decision record.
- If work is split across multiple systems, the issue should link to the authoritative artifact.
- The status should make the next action, owner, and expected date visible.

---

## 5. Ownership

Every issue, system, domain, recurring process, and critical tool must have a named owner. Critical areas must also have a named co-pilot.

Ownership means stewardship, not gatekeeping. The owner is responsible for visibility, quality, prioritization input, and escalation. The owner does not have to do all the work personally.

Minimum ownership standard:
- Owner named
- Co-pilot named for critical areas
- Escalation path documented
- Operational knowledge written down
- Review date visible

Orphaned work stays unresolved. Orphaned systems become risk.

---

## 6. Development and delivery principles

### 6.1 Continuous improvement

Run honest retrospectives. Focus on what could have worked better, what was learned, and what remediation actions will prevent recurrence.

A retrospective is not complete until action items have:
- owner
- due date
- expected outcome
- verification method

### 6.2 Automate repeated manual work

Look for repeated, error-prone, or high-volume manual work that can be automated for the team or for users. Automate when frequency, risk, or user impact justifies the cost.

### 6.3 Build for reuse with judgment

Prefer reuse when there is a credible second use case, a stable domain boundary, or a recurring pattern. Avoid speculative platform work for one-off needs. Generalize after the second real use, not before the first.

### 6.4 Build for change

Assume specifications and assumptions will change. Design solutions, tests, data flows, and processes so changes are localized and safe.

---

## 7. User enablement

Prefer enabling users over repeatedly doing manual service for them.

When users repeatedly ask the team for the same data, workflow, report, or operational action, evaluate whether the better answer is:
- documentation
- training
- self-service tooling
- reporting system improvement
- product/process change
- automation

The goal is not to avoid helping users. The goal is to help in a way that makes future help less necessary.

---

## 8. Data, reporting, and analysis artifacts

The team should answer business and analytics questions, not merely provide raw data. Conclusion beats insight; insight beats data dump.

### 8.1 Preferred artifact hierarchy

Prefer, in order:
1. A governed report, dashboard, or query in the reporting system
2. A shared query or reusable data artifact with source and assumptions documented
3. A shared spreadsheet only when the first two options are not practical
4. A one-time extract only when explicitly justified

Private copies of spreadsheets and unexplained extracts are anti-patterns.

### 8.2 Required methodology

Every artifact delivered to users must explain how it was obtained. Include, as appropriate:
- source data
- query or transformation logic
- date range
- filters
- assumptions
- freshness timestamp
- owner/contact
- link to the reporting system or source artifact

For quick internal communication, small dataset snippets may be shared as text/code together with the query or command used to produce them.

---

## 9. Delivery workflow

### 9.1 During refinement / planning

For each request:
- critically assess usefulness and expected outcome
- clarify scope and definition of done
- estimate effort
- identify owner and co-pilot where needed
- ask for advice early if uncertain
- attach or link relevant documentation
- record dependencies, risks, and assumptions
- decide whether the request is yes, no, or not yet

### 9.2 During execution

- Raise blockers immediately.
- Update the system of record when scope, risk, or timeline changes.
- Document relevant operational or technical context as work proceeds.
- Communicate before the due date if the commitment is at risk.

### 9.3 Definition of done

Work is done when:
- the agreed outcome is delivered or explicitly renegotiated
- tests/reviews/checks appropriate to the work are complete
- the requestor can verify the result
- the system of record is updated
- relevant documentation is attached or linked
- reporting or data artifacts include methodology
- follow-up risks, debt, or support needs are captured

---

## 10. Documentation, skills, and workflows

Default to AI-friendly Markdown files in source control for durable team documentation. Markdown is plain text, searchable, diffable, reviewable, and readable by humans and AI agents without proprietary tooling.

Use shared document systems for high-level collaboration, meeting notes, or stakeholder-facing summaries. Do not make them the canonical home for technical documentation, runbooks, operating procedures, or recurring workflows that the team must execute.

Represent recurring processes as skills and workflows. Each skill/workflow should include:
- when to use it
- required inputs
- ordered steps
- decision points
- expected outputs
- owner
- verification checklist
- escalation path

A process that only exists as prose is easy to ignore. A process represented as a skill/workflow can be executed, reviewed, improved, and used by AI agents.

---

## 11. Exceptions

Teams may adapt this SOP to their domain, but exceptions must be explicit. If a team uses a different threshold, workflow, or artifact standard, document the reason and review it periodically.

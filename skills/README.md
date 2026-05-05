# CTObot Skills Package

This directory contains the reusable CTO-focused skills that ship with CTObot.

## What’s inside

| Skill | Purpose |
|---|---|
| `cto-challenge-extraction` | Normalize an external CTO article, interview, or checklist into a short canonical challenge list. |
| `cto-operating-doc-red-team` | Compare `AGENTS.md` / `SOUL.md` against those challenges and surface practical execution gaps. |
| `cto-red-team-scorecard` | Produce a pass / partial pass / fail scorecard with missing artifacts and severity. |
| `cto-challenge-stress-test` | Evaluate an agentic CTO against common CTO challenge families and compare to the governing manual. |

## How to install

These skills are designed to be copied into the dot-directory of the tool you are using.

Examples:
- Claude Code: `.claude/skills/`
- OpenCode: `.opencode/skills/`
- Hermes: `~/.hermes/skills/`

Keep the same on-disk layout when copying:

```text
skills/<category>/<skill-name>/SKILL.md
```

If a skill includes a `references/` directory, copy that directory too so the skill keeps its supporting notes.

## How to use

1. Copy the desired skills into your tool’s dot-directory.
2. Start the tool from the repo or workspace that contains the target files.
3. Ask the agent to use the relevant skill, or load it explicitly if your tool supports that.

## Notes

- The skill content is intentionally concise and workflow-focused.
- The `references/` files capture durable session learnings and examples.
- If you adapt a skill for another tool, keep the trigger wording and output shape aligned so the skill stays portable.

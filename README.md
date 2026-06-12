# Client-Ready — free Claude Code skills for freelance web developers

Two free, production-quality **Claude Code skills** for freelancers and small agencies doing
client web work. No dependencies, install in one command.

- **`/project-intake`** — paste a messy client brief (email thread, call notes, voice-memo
  transcript), get back a structured spec with an **explicit out-of-scope list** (your
  scope-creep armor), a task-level estimate range, and open questions formatted to forward
  to the client verbatim. Run it before you quote anything.
- **`/pre-delivery-qa`** — a systematic pre-handoff sweep: placeholder debris, broken form
  states, test email addresses still wired in, debug mode left on, missing alt text — ending
  in a **SHIP / SHIP WITH NOTES / DO NOT SHIP** verdict. Run it before you call anything
  finished.

## Install

```bash
git clone https://github.com/Bleasure34/client-ready-free
cp -r client-ready-free/skills/* ~/.claude/skills/
```

Open Claude Code in any project — both skills are now available as `/project-intake` and
`/pre-delivery-qa`.

## Why these two skills

Most Claude Code skills are coding tricks. These run the *business* side of client work —
the part that decides whether a project is profitable before a line of code exists, and
whether the handoff is embarrassing after the last line is written.

They are 2 of the 8 skills in the **[Client-Ready Kit ($29)](https://clientreadykit.gumroad.com/l/dajgpk)**,
which covers the full client-project lifecycle:

| Stage | Skill | Free? |
|-------|-------|:-----:|
| Quoting | `/project-intake` — brief → spec + estimate | ✅ this repo |
| Takeovers | `/codebase-audit` — inherited code → client-readable health report | kit |
| Mid-project | `/change-request` — "can we just add…" → impact analysis + reply draft | kit |
| Delivery | `/pre-delivery-qa` — systematic handoff sweep | ✅ this repo |
| Launch | `/security-pass` — defensive review, findings cite file:line | kit |
| Launch | `/perf-pass` — fixes sorted by impact-per-hour | kit |
| Handoff | `/handoff-doc` — docs generated from your actual code | kit |
| Recurring | `/maintenance-proposal` — repo → tiered retainer proposal | kit |

The kit also includes guardrail hooks (env-file shield, force-push blocker for client repos)
and CLAUDE.md templates for Next.js, WordPress/PHP, and any-stack client projects.

**[Get the full kit → ](https://clientreadykit.gumroad.com/l/dajgpk)**

## License

MIT for everything in this repo. Use it, fork it, ship it.

---

*Topics: claude-code, claude-code-skills, ai-coding, freelance, web-development, agentic-coding*

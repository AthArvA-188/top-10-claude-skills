# Top 10 Claude Skills

A curated collection of 10 production-quality Claude Skills — each one a standalone `SKILL.md` file ready to upload directly to Claude.ai, Claude Code, or the Claude API.

Inspired by the [r/ClaudeAI community thread](https://www.reddit.com/r/ClaudeAI/comments/1sx44bc/drop_your_best_claude_skills_in_here/) and built from the best patterns across the Claude Skills ecosystem.

---

## Skills

| # | Skill | What it does |
|---|-------|--------------|
| 1 | [task-observer](./01-task-observer/SKILL.md) | Meta-skill that watches your sessions and improves your skill library automatically |
| 2 | [deep-code-review](./02-deep-code-review/SKILL.md) | Production-grade code review covering security, performance, correctness, and maintainability |
| 3 | [content-research-writer](./03-content-research-writer/SKILL.md) | Research-first writing assistant for long-form content with citations |
| 4 | [brainstorming](./04-brainstorming/SKILL.md) | Structured ideation that goes from rough idea to evaluated options |
| 5 | [meeting-insights](./05-meeting-insights/SKILL.md) | Analyzes transcripts for decisions, action items, and behavioral patterns |
| 6 | [software-architecture](./06-software-architecture/SKILL.md) | Clean Architecture, SOLID, design patterns, and refactoring guidance |
| 7 | [lead-research](./07-lead-research/SKILL.md) | ICP definition, prospect qualification, and outreach strategy |
| 8 | [internal-comms](./08-internal-comms/SKILL.md) | Status updates, incident reports, newsletters, and team announcements |
| 9 | [skill-creator](./09-skill-creator/SKILL.md) | Guided Q&A process to build new skills from scratch |
| 10 | [article-extractor](./10-article-extractor/SKILL.md) | Extracts and summarizes web articles with reliability signals |

---

## How to Use

### Claude.ai (web)

1. Go to **Settings → Capabilities** and enable **Code Execution**
2. Go to **Customize → Skills**
3. Click **+** → **Create skill** → Upload a ZIP
4. Each skill folder (e.g. `01-task-observer/`) needs to be zipped individually before uploading

**To zip a skill on Mac/Linux:**
```bash
zip -r task-observer.zip 01-task-observer/
```

**On Windows:** Right-click the folder → Send to → Compressed (zipped) folder

### Claude Code

```bash
# Copy a skill to your personal skills directory
cp -r 02-deep-code-review ~/.claude/skills/deep-code-review
```

### Claude API

Upload via the Skills API endpoint. See [Anthropic's documentation](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview) for details.

---

## Skill Structure

Every skill follows the standard format:

```
skill-name/
└── SKILL.md    # Required: frontmatter + instructions
```

The `SKILL.md` always starts with YAML frontmatter:

```yaml
---
name: skill-name
description: What it does and when to activate. Be specific.
---
```

The description is the most critical field — Claude reads it to decide whether to load the skill.

---

## Credits and Inspiration

- [rebelytics/one-skill-to-rule-them-all](https://github.com/rebelytics/one-skill-to-rule-them-all) — the original meta-skill concept
- [travisvn/awesome-claude-skills](https://github.com/travisvn/awesome-claude-skills) — the best skills directory in the ecosystem
- [ComposioHQ/awesome-claude-skills](https://github.com/ComposioHQ/awesome-claude-skills) — community skills collection
- [r/ClaudeAI](https://www.reddit.com/r/ClaudeAI/) — the community thread that inspired this collection

---

## Contributing

Found a bug or have an improvement? PRs welcome.

To add a new skill: create a folder with a `SKILL.md` file, following the format above. Update the README table. Submit a PR.

---

## License

MIT — use freely, modify freely, share freely.

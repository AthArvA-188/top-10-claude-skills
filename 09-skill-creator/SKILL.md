---
name: skill-creator
description: Guides you through building new Claude skills with a structured Q&A process. Use when you want to create a new skill from scratch, improve an existing one, or turn a repeated workflow into a reusable skill. Produces a ready-to-upload SKILL.md file.
---

# Skill Creator

An interactive skill-building process. You describe a workflow or pain point; I ask the right questions; together we produce a high-quality, ready-to-upload SKILL.md file.

## When to Create a Skill

A good skill candidate is anything you:
- Explain to Claude the same way more than 3 times
- Wish Claude understood about your specific domain, format preferences, or workflow
- Have to re-prompt every session because Claude's default approach doesn't fit your context

## The Build Process

### Step 1 — Intake Interview
Answer these questions (or let me ask them one at a time):

1. **What is the skill for?** Describe the task in plain language.
2. **When should it activate?** What triggers this skill — specific words, task types, file types?
3. **What does good output look like?** Share an example of a past output you loved, or describe it.
4. **What does bad output look like?** What does Claude typically get wrong on this task?
5. **Are there domain-specific rules?** Terminology, formats, frameworks, constraints to always follow?
6. **What context does Claude need?** Background that every session should start with.
7. **How long / what format?** Length, structure, headings, tone.

### Step 2 — Draft
Produce a SKILL.md with:
- YAML frontmatter (name + description)
- Clear task instructions
- Output format specification
- Concrete examples (good input → good output)
- Tips and edge case handling

### Step 3 — Review
Test the draft by describing 2-3 real scenarios you'd use it for. Refine until the description triggers reliably and the instructions produce the right output.

## SKILL.md Template

```markdown
---
name: your-skill-name
description: [One sentence: what it does and when to use it. Be specific — this is what Claude reads to decide whether to activate the skill.]
---

# [Skill Name]

[1-2 sentences: what this skill is and what problem it solves]

## When to Use
[Explicit triggers and conditions]

## Instructions
[Step-by-step process or framework for Claude to follow]

## Output Format
[Structure, length, tone, any required sections]

## Examples
**Input**: [Example prompt]
**Output**: [Expected result or description of it]

## Tips
[Edge cases, common mistakes to avoid, expert notes]
```

## Description Writing Guide

The description field is the most important part — it determines when Claude activates the skill. A good description:

✅ Names the specific task: "Use when writing SQL queries that need performance optimisation"
✅ Names the trigger: "Activates when user pastes a meeting transcript"
✅ Is specific enough to avoid false positives: "for Python async code" not "for code"

❌ Too vague: "Helps with writing"
❌ Too broad: "Use for any technical task"
❌ Missing trigger: only describes what it does, not when

## Quality Checklist

Before uploading:
- [ ] Does the name use only lowercase letters, numbers, and hyphens?
- [ ] Does the description tell Claude exactly when to activate?
- [ ] Are there at least 2 concrete examples?
- [ ] Does the output format section specify length, structure, and tone?
- [ ] Have you tested it against 3 different prompts?

## Tips

- Start simple. A skill with clear instructions beats a skill with elaborate but vague instructions.
- Test the description by asking Claude: "When would you use this skill?" If the answer doesn't match your intent, rewrite the description.
- One skill per workflow. Don't combine "code review + architecture + documentation" — create three focused skills that compose better.

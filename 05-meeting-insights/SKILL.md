---
name: meeting-insights
description: Analyzes meeting transcripts to surface behavioral patterns, extract decisions, flag unresolved issues, and identify follow-up actions. Use after any meeting where you have a transcript or detailed notes — especially useful for 1:1s, team syncs, retrospectives, and customer calls.
---

# Meeting Insights Analyzer

Turns a raw meeting transcript into structured intelligence: what was decided, what was avoided, who drove the conversation, and what needs to happen next.

## What It Analyzes

### Decisions Made
Explicit commitments and agreements. Each decision is tagged with:
- The decision itself
- Who owns it
- Any stated conditions or caveats

### Actions and Follow-ups
Every "I'll do X", "can you take Y", or implied commitment, with:
- Owner
- Due date (if mentioned)
- Dependency (if it blocks something else)

### Unresolved Issues
Topics that came up but weren't concluded — the things that will cause problems if they don't get addressed. Includes:
- Disagreements that were deferred
- Questions that were raised but not answered
- Topics that were tabled for "a future conversation"

### Behavioral Patterns
What the transcript reveals about the group dynamics:
- **Speaking ratio** — who dominated? who barely spoke?
- **Conflict avoidance** — were difficult topics skirted?
- **Decision quality** — were decisions made with clear rationale, or were they defaulted into?
- **Filler word density** — signals uncertainty or lack of preparation
- **Meeting purpose drift** — did the conversation stay on topic?

### Key Quotes
Verbatim pulls that capture the most important moments — commitments, insights, friction, or clarity.

## Output Format

```
## Meeting Summary
[2-3 sentences: what this meeting was about and what it accomplished]

## Decisions Made
| Decision | Owner | Notes |
|----------|-------|-------|

## Action Items
| Action | Owner | Due | Blocks |
|--------|-------|-----|--------|

## Unresolved Issues
[List with brief description of why each matters]

## Behavioral Observations
[What the dynamics reveal — keep this constructive and specific]

## Follow-up Recommendation
[The most important thing to do before the next meeting]
```

## Usage

Paste the transcript (or detailed notes) and optionally specify:
- Meeting type (1:1, team sync, customer call, retrospective, etc.)
- What you're most interested in (e.g., "focus on action items" or "I'm concerned about team dynamics")
- Whether participants should be anonymised in the output

## Examples

**Input**: Customer call transcript
**Focus**: Extract product feedback, objections raised, and implied commitments made by your team.

**Input**: Team retrospective notes
**Focus**: Surface patterns across multiple retros to identify recurring issues.

**Input**: 1:1 with a direct report
**Focus**: Track stated goals vs. actual progress, and flag anything that suggests blockers.

## Tips

- The behavioral patterns section is often more valuable than the action items — what's avoided tells you as much as what's said
- Compare the action items from this analysis against last meeting's — outstanding actions that carry over are a signal worth investigating
- If you're running the meeting, use the output to design the next agenda: start with unresolved issues from this meeting

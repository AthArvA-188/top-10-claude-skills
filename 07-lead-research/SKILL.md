---
name: lead-research
description: Identifies and qualifies high-quality leads by analyzing your product or service, searching for target companies and contacts, and providing actionable outreach strategies. Use when building a prospect list, preparing for outbound sales, researching a target account before a call, or building an ICP (Ideal Customer Profile).
---

# Lead Research Assistant

A structured lead qualification and research framework. Moves from product understanding → ICP definition → prospect identification → contact research → outreach strategy.

## Phase 1 — Define the ICP (Ideal Customer Profile)

Before researching any prospect, define who you're looking for:

| Attribute | Example |
|-----------|---------|
| Company size | 50-500 employees |
| Industry | SaaS, fintech, e-commerce |
| Geography | North America, EMEA |
| Tech stack signals | Uses Salesforce, Segment, Intercom |
| Growth signals | Hiring, recent funding, new product launches |
| Pain signal | Job postings mentioning a specific problem |
| Buyer role | VP of Engineering, Head of Growth, CFO |
| Disqualifiers | Bootstrapped only, < $1M ARR, government contracts |

If you don't have an ICP yet, provide 3-5 of your best existing customers and I'll extract the pattern.

## Phase 2 — Company Research

For each target company, surface:

**Firmographic data**
- Founded, employee count, funding stage and amount, HQ
- Revenue estimate (if available)

**Strategic signals**
- Recent news (funding, expansion, leadership changes, product launches)
- Job postings (what problems are they hiring to solve?)
- Tech stack (from job postings, BuiltWith, Wappalyzer)
- Competitors (are they actively competing in a space you serve?)

**Relevance score**
Rate 1-5 against your ICP. Flag why they score high or low.

## Phase 3 — Contact Research

For each target company, identify the right people:

- **Primary contact**: the person with budget authority for your solution
- **Champion candidate**: the person who would use/benefit from your solution most
- **Blocker**: who would likely object and how to address them preemptively

For each contact, find:
- Current role and tenure (LinkedIn)
- Recent activity (posts, comments, interviews)
- Mutual connections or warm paths in
- Direct contact (email pattern + tool verification where possible)

## Phase 4 — Outreach Strategy

For each high-scored prospect, produce:

**Personalisation angle**
Specific to this company and contact — not generic. Should reference something they've said, published, or done recently.

**Opening hook**
One sentence that earns the next sentence. Not "I noticed you're the VP of X" — that's about you. Something that shows you understand their world.

**Value statement**
What specific pain does your product solve for this company, given what you know about them?

**Call to action**
One clear, low-friction ask. Not "let me know if you want a demo" — specific: "Would a 20-min call Thursday or Friday work?"

## Output Format

```
## ICP Summary
[What you're targeting and why]

## Company Profile: [Name]
- Fit score: [1-5]
- Why they fit / why they don't
- Key signals: [funding, hiring, tech stack, news]

## Target Contacts
| Name | Role | Why them | Contact |
|------|------|----------|---------|

## Outreach Draft
[Personalised opening message for primary contact]

## Next Steps
[Specific actions to move this account forward]
```

## Tips

- The best personalisation comes from recent activity — a LinkedIn post from last week beats a funding announcement from 18 months ago.
- A warm introduction beats cold outreach by 10x. Before writing a cold email, check every mutual connection.
- Don't over-research. 20 minutes per account is enough. The signal you need is usually in the first 5 minutes; the rest is procrastination.

---
name: article-extractor
description: Extracts full article text and metadata from web pages, then produces a clean structured summary with key claims, supporting evidence, author stance, and original source link. Use when researching a topic, fact-checking a claim, saving content for reference, or comparing coverage across multiple sources.
---

# Article Extractor

Fetches and processes web articles into clean, structured summaries. Separates facts from opinions, surfaces the author's core argument, and makes it easy to compare multiple sources side by side.

## What It Produces

For each article:

### Metadata
- Title, author, publication, date
- Word count / estimated read time
- Original URL

### Summary (100-150 words)
Plain language summary of the article's main argument and conclusions. No editorialising — just what the article says.

### Key Claims
A numbered list of the article's most important factual claims or arguments, each with:
- The claim itself
- Whether it's a fact (cites a source) or opinion (author's interpretation)
- Strength of evidence (strong / weak / assertion only)

### Author's Stance
1-2 sentences on the author's perspective, biases, or framing — especially for opinion or analysis pieces.

### Notable Quotes
1-3 direct quotes that best represent the article's core point or most surprising claim. Under 15 words each.

### Reliability Signals
Quick flags for:
- Publication credibility
- Source quality (primary sources cited? studies named? "experts say" without attribution?)
- Date relevance (is this information still current?)
- Potential bias (who publishes this? what's their interest?)

## Output Format

```
## Article: [Title]
**Source**: [Publication] | **Author**: [Name] | **Date**: [Date]
**URL**: [Link]

### Summary
[100-150 word plain summary]

### Key Claims
1. [Claim] — [fact/opinion] — [evidence strength]
2. ...

### Author's Stance
[1-2 sentences]

### Notable Quotes
- "[Quote]"
- ...

### Reliability
- Publication: [signal]
- Sources: [signal]
- Recency: [signal]
- Bias note: [if applicable]
```

## Multi-Article Mode

Provide 2+ URLs and specify a question or topic. The extractor will:
1. Process each article individually
2. Produce a comparison showing where sources agree, disagree, or have different emphases
3. Flag any claims that appear in only one source

Example output:
```
## Cross-Source Analysis: [Topic]

**Consensus across sources**: [What all sources agree on]

**Points of disagreement**:
| Claim | Source A | Source B | Source C |
|-------|----------|----------|----------|

**Unique to one source** (treat with extra scrutiny):
- [Source A only]: [claim]
```

## Usage

**Single article**: Provide a URL or paste the full text.
**Multi-article comparison**: Provide 2-5 URLs + the question you're researching.
**Fact-check mode**: Provide a specific claim + one or more sources. Output focuses on whether the source actually supports the claim.

## Tips

- Paywalled articles can't be fetched, but you can paste the text directly.
- For fast-moving topics, pay attention to the Recency flag — an article from 18 months ago may be outdated even if it's from a credible source.
- The "notable quotes" section is intentionally short. If the most important thing in a piece can't fit in 15 words, that's usually a sign the piece is poorly argued or overly hedged.
- Use multi-article mode when you're researching something important. Single-source research is the fastest path to a skewed understanding.

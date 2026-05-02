---
name: deep-code-review
description: Production-grade code review skill. Use when reviewing pull requests, auditing code quality, checking for security vulnerabilities, evaluating architecture decisions, or preparing code for production. Covers security, performance, maintainability, and correctness.
---

# Deep Code Review

A structured, production-grade code review framework. Goes beyond "does this work" to evaluate security, performance, maintainability, and architectural soundness.

## Review Dimensions

For every review, evaluate across these dimensions in order of severity:

### 1. Security (P0 — block on any finding)
- Injection vulnerabilities (SQL, XSS, command injection)
- Authentication/authorisation bypasses
- Secrets hardcoded in source (API keys, passwords, tokens)
- Insecure deserialization
- Exposed internal error details in responses
- Missing input validation on user-controlled data

### 2. Correctness (P0)
- Logic errors, off-by-one, null/undefined edge cases
- Race conditions and concurrency issues
- Error handling completeness (are all failure modes handled?)
- Data loss risks

### 3. Performance (P1)
- N+1 queries or missing database indexes
- Unbounded loops over large datasets
- Missing caching opportunities
- Blocking I/O on hot paths
- Memory leaks

### 4. Maintainability (P1)
- Functions doing more than one thing
- Magic numbers/strings without named constants
- Missing or misleading comments on complex logic
- Naming that doesn't reflect intent
- Duplicated logic that should be extracted

### 5. Test Coverage (P2)
- Happy path tested but edge cases missing
- No tests for security-sensitive paths
- Tests that test implementation, not behaviour

### 6. Architecture (P2)
- Violates existing patterns in the codebase
- Tight coupling that will cause pain later
- Missing abstractions
- Premature optimisation

## Output Format

Produce a review in this structure:

```
## Summary
[1-2 sentences: overall quality signal and key concerns]

## Blocking Issues
[P0 items that must be fixed before merge]

## Should Fix
[P1 items — non-blocking but expected before merge in most teams]

## Nice to Have
[P2 items — suggestions, not requirements]

## Positives
[What was done well — always include at least one]
```

## Usage

Provide the code (paste, file, or diff) and optionally specify:
- Language/framework
- Context ("this handles user authentication")
- Review focus ("prioritise security" or "quick readability pass only")

## Examples

**Input**: "Review this Express.js middleware for auth"
**Approach**: Focus on P0 security first (JWT validation, timing attacks, header injection), then correctness.

**Input**: "Review this data pipeline for performance"
**Approach**: Focus on P1 performance (batch sizes, streaming, index usage), then correctness.

**Input**: "Quick pass on this utility function"
**Approach**: Correctness and naming only. Skip architecture and test coverage sections.

## Tips

- Always ask for context if the code's purpose is unclear — a review without context misses half the issues
- For large PRs (500+ lines), ask the author to split by concern before reviewing
- When flagging security issues, provide a concrete exploit scenario, not just "this could be exploited"

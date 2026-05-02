---
name: software-architecture
description: Implements and evaluates software design patterns including Clean Architecture, SOLID principles, domain-driven design, and system design best practices. Use when designing new systems, refactoring existing code, evaluating architectural trade-offs, or learning design patterns through concrete examples.
---

# Software Architecture

A structured approach to software design that prioritises maintainability, testability, and scalability. Covers pattern selection, SOLID principles, architecture evaluation, and refactoring toward better design.

## Core Principles

### SOLID (apply to every design decision)
- **S**ingle Responsibility: one class/module = one reason to change
- **O**pen/Closed: open for extension, closed for modification
- **L**iskov Substitution: subtypes must be substitutable for their base types
- **I**nterface Segregation: many specific interfaces > one general interface
- **D**ependency Inversion: depend on abstractions, not concretions

### Architecture Layers (Clean Architecture)
```
Entities (domain objects, business rules)
    ↑
Use Cases (application business logic)
    ↑
Interface Adapters (controllers, presenters, gateways)
    ↑
Frameworks & Drivers (databases, web frameworks, UI)
```

The dependency rule: inner layers must not know about outer layers. Data flows inward; dependencies point inward.

## Pattern Selection Guide

| Problem | Pattern | When to use |
|---------|---------|-------------|
| Complex object creation | Factory / Builder | When construction logic is non-trivial |
| Need single shared instance | Singleton | Rare — prefer dependency injection |
| Notify many objects of state change | Observer / Event Bus | Decoupling producers from consumers |
| Vary behaviour at runtime | Strategy | Swappable algorithms |
| Wrap incompatible interfaces | Adapter | Legacy integration |
| Simplify complex subsystem | Facade | Reducing interface surface area |
| Separate query from command | CQRS | Read-heavy or write-heavy systems |
| Rebuild state from events | Event Sourcing | Audit trails, temporal queries |
| Decentralise data management | Microservices | When teams need independent deployments |

## Evaluation Framework

When reviewing an existing architecture, ask:

1. **Testability**: can the business logic be tested without the database, UI, or network?
2. **Changeability**: can you swap the database or framework without touching business logic?
3. **Readability**: can a new engineer understand what a module does from its name and public interface?
4. **Cohesion**: are things that change together, grouped together?
5. **Coupling**: can a module be changed without rippling through unrelated modules?

Score each 1-5. Anything below 3 on testability or changeability is a priority refactor target.

## Common Anti-Patterns to Flag

- **Anemic domain model**: domain objects are just data bags; business logic is scattered in services
- **God class**: one class knows too much about too many things
- **Feature envy**: a method that uses another class's data more than its own
- **Spaghetti dependencies**: circular imports or hidden coupling through global state
- **Premature abstraction**: interfaces for things that only have one implementation
- **Leaky abstractions**: infrastructure concerns bleeding into business logic

## Output Modes

### Design a new system
Provide: requirements, constraints (scale, team size, deployment model), existing tech stack.
Output: layer diagram, key interfaces, data flow, technology recommendations with rationale.

### Review existing code
Provide: the code or description of the current structure.
Output: SOLID violations found, pattern suggestions, refactoring roadmap ordered by impact.

### Explain a pattern
Provide: the pattern name and your current understanding.
Output: plain language explanation, concrete code example in your language, when to use vs. when to avoid.

## Tips

- Start with testability. If business logic can't be unit-tested in isolation, the architecture is wrong regardless of what patterns are used.
- Clean Architecture is a direction, not a destination. Every codebase lives on a spectrum — the goal is continuous improvement, not perfection.
- Before recommending a pattern, ask: does the current code actually have the problem this pattern solves? Over-engineering is a real cost.

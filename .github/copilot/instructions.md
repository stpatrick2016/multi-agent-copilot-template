# Global Copilot Instructions

All agents must follow these global rules.

## Engineering Philosophy

- Prefer the smallest working solution first
- Architecture before implementation
- Avoid abstractions without immediate need
- Keep responsibilities explicit
- Optimize readability before cleverness

## File Rules

- Avoid files larger than 300 lines unless justified
- Split files only when responsibility is clear
- Avoid hidden dependencies between modules

## Naming Rules

- Use explicit names
- Avoid ambiguous abbreviations
- Prefer domain language over generic labels

## Testing Rules

- Non-trivial logic requires tests
- Edge cases must be covered
- Regression-sensitive code must have repeatable checks

## Review Rules

- Reject duplication
- Reject oversized methods
- Reject hidden coupling
- Request tradeoffs before major structural changes

## Architecture Rules

- Interfaces before implementation when systems interact
- Record major decisions in architecture-log.md
- Avoid changing architecture without explicit reason

## Complexity Rule

- Prefer simple implementation unless complexity is required now

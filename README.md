# Copilot Multi-Agent Template

A lightweight reusable template for running a structured multi-agent development workflow with GitHub Copilot inside VS Code.

The goal is simple: keep one **Manager** agent in control, activate only the agents relevant to the current project, and enforce a repeatable development sequence.

---

# Recommended Startup Flow

1. Copy this template into a new repository.
2. Select the closest project preset from `.github/copilot/presets/`.
3. Update `.github/copilot/project-config.md` to enable only relevant agents.
4. Create or review `.github/copilot/instructions.md` before first implementation. This file defines the global coding contract for all agents.
5. Start every feature by asking the Manager agent to read `project-config.md`.
6. Follow the standard execution order:

   * Architect
   * Coder
   * Tester
   * Optional specialists
   * Reviewer
   * Manager approval
7. Record major technical decisions in `project-intelligence/architecture-log.md`.

---

# Recommended Default Active Agents

Keep these active in most projects:

* manager
* architect
* coder
* tester
* reviewer

Optional agents should only be enabled when needed:

* security
* performance
* devops
* database
* ui
* docs
* unity-agent

---

# Practical Advice

* Start lean: too many agents create noise.
* Architecture should always happen before implementation.
* Tests should exist before final approval.
* Optional agents should only review relevant work.
* Keep `project-config.md` current, because Manager decisions depend on it.
* Use `architecture-log.md` to avoid repeating design mistakes.

---

# Brief Workflow Philosophy

This template is not about simulating many AI agents for complexity.
It is about forcing clean engineering discipline:

* one orchestrator
* clear task boundaries
* explicit review stages
* reusable project memory

The system works best when each agent has a narrow responsibility and the Manager enforces order.

---

# Example First Prompt for Manager

Use this at the beginning of every new feature or task:

`Read project-config.md, identify active agents, and propose execution plan for this task before any code is written.`

This ensures orchestration happens before implementation.

---

# Minimal Repository Bootstrap Checklist

Before starting real work, confirm:

* repository name is final
* folder structure matches project type
* project preset is selected
* project-config.md reflects active agents
* testing framework is defined
* branch naming convention is agreed
* first architecture log entry exists

Recommended branch naming examples:

* feature/auth-system
* fix/save-loading
* refactor/ui-layout

---

# Agent Invocation Examples

## New Feature

1. Manager reads task
2. Architect defines structure
3. Coder implements
4. Tester writes tests
5. Reviewer checks final quality

## Bug Fix

1. Manager identifies affected files
2. Tester defines failure case first
3. Coder fixes root cause
4. Reviewer checks regression risk

## Refactor

1. Architect defines target structure
2. Coder refactors incrementally
3. Tester verifies no regression
4. Reviewer checks readability

## Security Review

1. Security agent reviews exposed surfaces
2. Reviewer checks implementation impact
3. Manager approves only after issues resolved

---

# How to Talk to Each Agent Effectively

## Manager

Ask for sequencing, not code.

Good:
`Break this task into execution stages using active agents.`

## Architect

Ask for boundaries.

Good:
`Design file structure and interfaces before implementation.`

## Coder

Ask for exact implementation.

Good:
`Implement only approved architecture.`

## Tester

Ask for failure coverage.

Good:
`Write tests covering edge cases and regressions.`

## Reviewer

Ask for strict criticism.

Good:
`Reject unclear naming, duplication, and complexity.`

---

# What Manager Should Do When Agents Disagree

If two agents conflict:

1. Architect wins on structure.
2. Security wins on safety.
3. Tester wins on reproducible failures.
4. Reviewer wins on maintainability.
5. Manager resolves only after explicit comparison.

Always request:

`List tradeoffs before choosing.`

---

# How to Prevent Copilot from Overengineering

Always enforce:

* smallest working solution first
* no abstraction without immediate need
* no extra files without clear responsibility
* no patterns copied without reason

Useful instruction:

`Prefer simple implementation unless complexity is required now.`

---

# Scaling From Solo Project to Production Repository

## Solo Stage

Use only:

* manager
* architect
* coder
* tester
* reviewer

## Medium Complexity

Add:

* security
* performance

## Production Scale

Add only when required:

* devops
* database
* docs
* failure-analysis

Do not activate all agents by default.

---

# Advanced Operating Principle

The system should remain modular.

Manager decides:

* which agents are needed
* which agents can be skipped
* when optional review adds value

A smaller active set almost always produces better results than a full agent stack.

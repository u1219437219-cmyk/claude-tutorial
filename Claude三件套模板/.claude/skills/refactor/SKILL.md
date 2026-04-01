---
name: refactor
description: Refactor code with tight scope and behavior-preserving discipline. Use when improving structure, readability, maintainability, or simplifying code without intentionally changing behavior.
---

# Refactor Skill

Use this skill when the goal is to improve code structure, readability, or maintainability while preserving behavior.

## Refactor Goals

Focus on:

1. Clarifying the refactor scope
2. Preserving existing behavior
3. Reducing complexity without broad churn
4. Keeping changes easy to review
5. Explaining validation and remaining risks

## Refactor Rules

- Keep the scope tight
- Do not mix refactoring with unrelated feature work
- Prefer small, reviewable steps
- Preserve existing behavior unless explicitly told otherwise
- If behavior may change, call it out clearly before proceeding

## Output Format

### Refactor Scope

- What is being cleaned up
- Why it needs refactoring

### Planned Changes

- What structure will improve
- What will stay behaviorally the same

### Changes Made

- Files changed
- What was simplified or clarified

### Validation

- Tests run
- Manual checks performed

### Residual Risks

- Any possible behavior drift or missing coverage

## Recommended Flow

1. Define scope
2. Inspect affected code
3. Make the smallest structural improvement
4. Validate behavior
5. Summarize risks and outcomes

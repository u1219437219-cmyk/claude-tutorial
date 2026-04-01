---
name: feature
description: Implement scoped features with a plan-first, low-risk workflow. Use when the user requests a new feature, enhancement, or behavior change.
---

# Feature Skill

Use this skill when implementing a new feature or enhancement.

## Feature Goals

Focus on:

1. Understanding the request clearly
2. Identifying affected modules and files
3. Proposing a small, realistic implementation path
4. Implementing with minimal unnecessary change
5. Explaining validation and residual risk

## Feature Rules

- Do not jump into code before the scope is understood
- Prefer small, incremental implementation over broad rewrites
- Reuse existing patterns where possible
- Avoid speculative abstractions
- If the feature is larger than expected, surface the scope clearly

## Output Format

### Scope

- What the feature is
- What parts of the system it touches

### Implementation Plan

- Short step-by-step path

### Changes Made

- What files changed
- What behavior was added or modified

### Validation

- Tests run
- Manual checks

### Residual Risks

- Any follow-up concerns or missing coverage

## Recommended Flow

1. Understand the feature
2. Identify affected files
3. Outline a small implementation plan
4. Implement with minimal scope
5. Validate and summarize

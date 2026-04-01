---
name: review
description: Review frontend changes for UI regressions, interaction consistency, state complexity, test gaps, and maintainability. Use when reviewing frontend code, components, pages, or patches.
---

# Frontend Review Skill

Use this skill when reviewing frontend changes.

## Review Goals

Focus on:

1. UI regression risk
2. Interaction consistency
3. Component boundary clarity
4. State management complexity
5. Style and responsive impact
6. Test gaps

## Review Output Format

### Summary

- Overall risk level: Low / Medium / High
- Main concern areas

### Findings

For each finding, include:

- What is the issue
- Where it is
- Why it matters to users or maintainability
- Suggested fix or follow-up

### Validation

- What should be tested manually
- What looks covered by tests
- What is missing

### Residual Risks

- Any UI, interaction, or responsive risks that may still remain

## Review Style

- Findings first
- Prioritize behavior and user-facing risks over style nits
- Be specific about what may regress on screen or in interaction

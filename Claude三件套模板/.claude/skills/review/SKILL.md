---
name: review
description: Review code changes for regression risk, edge cases, test gaps, and maintainability. Use when reviewing code, pull requests, patches, or proposed changes.
---

# Review Skill

Use this skill when the user asks to review code, assess a change, inspect a patch, or look for risks before merging.

## Review Goals

Focus on:

1. Regression risk
2. Edge cases
3. Test gaps
4. Maintainability
5. Unnecessary complexity

If the project is frontend-heavy, also consider:

- UI regressions
- interaction consistency
- state management complexity

If the project is backend-heavy, also consider:

- API contract changes
- data consistency risks
- error handling and logging

## Review Output Format

### Summary

- Overall risk level: Low / Medium / High
- Main concern areas

### Findings

For each finding, include:

- What is the issue
- Where it is
- Why it matters
- Suggested fix or follow-up

### Testing

- What looks covered
- What is missing
- What should be verified manually if tests are absent

### Residual Risks

- Anything that may still be risky even if no clear bug is found

## Review Style

- Findings first
- Keep summaries brief
- Prioritize behavior changes over style nits
- Be specific about risk, not vague
- If there are no major findings, say so clearly

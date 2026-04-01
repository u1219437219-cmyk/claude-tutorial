---
name: bugfix
description: Investigate and fix frontend bugs with a root-cause-first workflow. Use when the issue involves UI behavior, state bugs, event handling, rendering, or style regressions.
---

# Frontend Bugfix Skill

Use this skill when handling frontend bugs.

## Bugfix Goals

Focus on:

1. Understanding the user-visible issue
2. Identifying the most likely root cause
3. Narrowing relevant pages, components, state, and styles
4. Proposing the smallest safe fix
5. Explaining how to validate the result

## Bugfix Rules

- Do not jump straight to code changes if the cause is unclear
- Prefer fixing the actual source of the UI or state issue
- If interaction is broken, trace event flow and state updates
- If layout is broken, trace style scope and responsive behavior
- Keep fixes small and explain regression risks

## Output Format

### Bug Summary

- What the user sees
- What should happen instead

### Likely Causes

- Ranked list of likely causes

### Relevant Files

- Pages, components, hooks, styles, or services worth inspecting

### Minimal Fix Plan

- Smallest likely safe fix

### Validation

- Manual interaction checks
- Relevant tests to run

### Residual Risks

- Any remaining UI or state risks

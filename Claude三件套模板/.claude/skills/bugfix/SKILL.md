---
name: bugfix
description: Investigate and fix bugs with a root-cause-first workflow. Use when the user reports a bug, regression, error, intermittent issue, or asks for a minimal safe fix.
---

# Bugfix Skill

Use this skill when the task is to diagnose and fix a bug, regression, failing behavior, or unclear issue.

## Bugfix Goals

Focus on:

1. Understanding the issue clearly
2. Identifying the most likely root cause
3. Narrowing the relevant files and execution path
4. Proposing the smallest safe fix
5. Explaining how to validate the result

## Bugfix Rules

- Do not rush to change code before the likely cause is clear
- Prefer fixing the root cause, not masking the symptom
- If the cause is uncertain, rank the hypotheses and explain them
- Keep the fix as small as possible
- Explicitly call out regression risks and missing tests

## Output Format

### Bug Summary

- What is happening
- What should happen instead

### Likely Causes

- Ranked list of likely causes

### Relevant Files

- Files or modules most worth inspecting

### Minimal Fix Plan

- Smallest safe change to likely solve the issue

### Validation

- What tests to run
- What manual checks to perform if tests are missing

### Residual Risks

- What may still be risky after the fix

## Recommended Flow

When handling a bug:

1. Restate the issue
2. Analyze likely causes
3. Narrow the affected area
4. Propose the minimal fix
5. Apply the fix only after the path is clear
6. Explain validation and residual risks

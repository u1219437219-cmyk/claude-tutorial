---
name: bugfix
description: Investigate and fix backend bugs with a root-cause-first workflow. Use when the issue involves APIs, data correctness, background jobs, concurrency, logs, or intermittent server behavior.
---

# Backend Bugfix Skill

Use this skill when handling backend bugs.

## Bugfix Goals

Focus on:

1. Understanding the failing behavior
2. Identifying the most likely root cause
3. Narrowing affected interfaces, services, jobs, or data paths
4. Proposing the smallest safe fix
5. Explaining validation and residual risk

## Bugfix Rules

- Do not jump straight to code changes if the cause is unclear
- Prefer fixing the actual root cause, not masking symptoms
- Use logs, call paths, and data flow to narrow the issue
- Call out consistency, contract, and concurrency risks explicitly
- Keep the fix small and explain regression risks

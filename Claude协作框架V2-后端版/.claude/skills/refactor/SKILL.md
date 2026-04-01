---
name: refactor
description: Refactor backend code with tight scope and behavior-preserving discipline. Use when simplifying service logic, data flow, module boundaries, or operational clarity without intentionally changing behavior.
---

# Backend Refactor Skill

Use this skill when improving backend structure while preserving behavior.

## Refactor Goals

Focus on:

1. Tight scope
2. Preserved behavior and compatibility
3. Simpler service and data flow logic
4. Lower operational risk
5. Clear validation

## Refactor Rules

- Do not mix refactoring with unrelated feature work
- Preserve existing contracts unless explicitly told otherwise
- Be careful around data, transactions, caching, and jobs
- Prefer small, reviewable steps

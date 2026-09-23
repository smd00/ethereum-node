---
name: code-review
description: Review pull requests in this repository using its architecture, domain rules, and test workflow. Use for every pull request or diff in this repository.
---

# Repository-aware code review

Read the changed files and enough surrounding code to trace each changed behavior from its caller to its side effects. Before reviewing, read any repository guidance that exists (`AGENTS.md`, `.github/copilot-instructions.md`, `README.md`, and relevant docs or CI workflows). Use the actual dependency manifest and scripts to identify valid test commands. Treat guidance as context, then check its claims against the current code.

Focus on concrete defects: incorrect behavior, authorization bypasses, leaked secrets, data loss, unsafe migrations, races, broken error handling, and deployment or compatibility failures. For UI changes, check keyboard and screen reader behavior when relevant. For external integrations, check validation, retries, timeouts, and idempotency. Follow the data and call sites across files; do not assume the diff alone shows the full effect.

Use the built-in GitHub MCP context when an issue, linked pull request, or repository history explains the intended behavior. Use Playwright MCP only when exercising a relevant UI flow can establish whether a suspected defect exists. Do not perform writes or destructive actions while gathering review evidence.

Report only actionable findings. For each, cite the changed file and line, describe a realistic input or sequence that triggers the problem, explain the user or system impact, and suggest the smallest sound fix. State uncertainty when evidence is incomplete. Skip formatting and naming comments unless they hide a real defect. Do not invent repository rules, test results, or commands.

---
name: documentation-instructions-update
description: Workflow command scaffold for documentation-instructions-update in CIPP-API.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /documentation-instructions-update

Use this workflow when working on **documentation-instructions-update** in `CIPP-API`.

## Goal

Update or add documentation and AI instructions, typically in .github/instructions or .github/agents, often together in a single commit.

## Common Files

- `.github/instructions/*.md`
- `.github/agents/*.md`
- `.github/copilot-instructions.md`
- `.gitignore`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit or add markdown files in .github/instructions/ and .github/agents/
- Optionally update .gitignore or related meta files
- Commit all documentation changes together

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.
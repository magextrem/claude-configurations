# CLAUDE.md

Coding guidelines. Bias toward caution; use judgment on trivial tasks.

## Think Before Coding
- State assumptions explicitly; surface multiple interpretations instead of picking silently
- If uncertain or unclear, stop and ask before implementing, not after mistakes. Don't assume

## Simplicity First
- Minimum code that solves the problem: if it could be 50 lines, don't write 200
- Nothing speculative: no extra features, abstractions, flexibility, or error handling for impossible cases

## Surgical Changes
- Edit only what the request requires; every changed line must trace to it
- Don't improve adjacent code; match existing style even if you'd do it differently
- Mention unrelated dead code — don't touch it
- Remove only imports/variables your own changes orphaned

## Goal-Driven Execution
- Define verifiable success criteria before starting
- For multi-step tasks, state a short plan with a verify step per item

## Token Efficiency
- Grep before reading; use offset+limit — never full reads when partial suffices
- Batch independent tool calls; stop chains early when the answer is clear
- For many repeated actions, write a script instead of chaining tool calls
- Suggest a skill or reusable approach when the same pattern recurs
- Responses: one sentence per update, no summaries or diff recaps unless asked

## Code Comments
- Single line only, no multi-line blocks; key info only, nothing superfluous or obvious

## Commit Hygiene
- Commit messages, PR descriptions, code comments and any repo-committed text read as if written solely by the human user: never mention Claude, AI, or an assistant, no "Co-Authored-By: Claude" (or similar) trailers
- Follow Conventional Commits (https://www.conventionalcommits.org): `<type>[optional scope]: <description>`, types like feat/fix/chore/docs/refactor/test/perf/build/ci, `!` or a `BREAKING CHANGE:` footer for breaking changes

## File Locations
- Save scripts and other files meant to be kept inside the current project (e.g. `scripts/`), never in /tmp, /private/tmp, the scratchpad or other global dirs unless the user explicitly asks

# User-level Claude Code instructions

1. Be honest. Fix mistakes instead of hiding them.
2. Don’t assume. Don’t hide confusion. Surface tradeoffs.
3. Minimum code that solves the problem. Nothing speculative.
4. Touch only what you must. Clean up only your own mess.
5. Define success criteria. Loop until verified.
6. State the principle before implementing. Audit every place it applies. Tests verify; they don't define scope.
7. Batch only independent work. If a call needs another's output or success, sequence them. If unsure, sequence them.
8. Treat every reported outcome as a claim. Confirm it against ground truth before you build on it or call it done.

## Code rules

Follow these rules when writing code.

1. For better clarity, always specify types in typed languages (e.g. Crystal, Go) even if they aren't explicitly required.

## Beads (bd) issue tracker

When a project uses **bd (beads)** for issue tracking, the following expectations apply.

### Issue content expectations

Every bd issue must have a populated description. Don't just restate the title — a reader should be able to act on the issue without asking.

A good description answers: **what** (the change), **why** (motivation), **scope** (in/out), and **acceptance** (how we know it's done).

Practical rules when creating issues:
- Pass multi-line descriptions via HEREDOC, not inline strings — shell quoting has silently dropped payloads before (issues have shipped with empty descriptions from `bd create --description=...` calls).
- **Verify with `bd show <id>` after every create.** If `DESCRIPTION: (none)`, re-run as `bd update <id> --description="..."` with a HEREDOC.
- Prefer `--acceptance` for testable criteria and `--design` for decision rationale; reserve the description body for what/why/scope.
- Run `bd lint` on touched issues before handing off.

# Collaboration Guidelines

This repository is worked on collaboratively by multiple people (and multiple Claude models).
The following rules must be followed regardless of the model in use.

## Communication

- **[STRICT] Never speak for the user or fabricate their words.** This is the most important rule.
  - Claude must never preemptively write a reply the user has not yet given ("yes", "sure", "go ahead", etc.).
  - Never output speaker markers or any utterance impersonating the user in the response text.
  - After asking a question, end the turn there. Always wait for the user's actual answer. Do not proceed until it arrives.
- **Ask one question at a time.** Even when several things need confirming, ask one, get an answer, then ask the next.
- **For large or multi-step work, state what you intend to do before starting.** Do not launch into big actions; declare the plan first, then proceed.

## Language

- **Communicate with the user in Japanese.**
- **Write code comments in English.**
- **Write commit messages in English** (see the Commits section).

## Commits

- **Claude must not commit without permission.** Run `git commit` only after receiving explicit permission ("you may commit") via the procedure below. Never commit otherwise.
- **Do not add Claude's signature to commit messages.** Never append lines like `🤖 Generated with Claude Code` or `Co-Authored-By: Claude`.
- **Commit message format is "prefix: one-line summary".**
  - The summary is in English, written in the imperative mood, lowercase, with no trailing period.
  - Always use one of the prefixes in the table below, and keep them consistent.

| Prefix | Purpose |
| --- | --- |
| `feat:` | New feature / new file or data |
| `fix:` | Bug fix |
| `docs:` | Documentation (README, comments, etc.) |
| `refactor:` | Restructuring/renaming/moving without changing behavior |
| `test:` | Adding or fixing tests |
| `chore:` | Config, build, dependencies, chores (`.gitignore`, Makefile, etc.) |
| `perf:` | Performance improvement |
| `style:` | Formatting only (whitespace, indentation, no behavior change) |

Examples:

```
feat: add graph enumeration algorithm
fix: correct crossing detection
docs: add build instructions to README
```

### Procedure when asked to "commit"

1. **Review the diff** (`git status` / `git diff`).
2. **Split changes into meaningful groups.**
3. **Propose a commit message per group** (following the format above).
4. **Confirm with the user that they are acceptable.**
5. Once the messages are approved, **ask again whether it is OK to actually commit.**
6. Branch on the response:
   - "You may commit" → **Claude commits.**
   - "No (I'll do it myself)" → **Claude does not commit.** The human presses the commit button in VSCode.

## Push

- **Never push without permission.** Always confirm with the user before running `git push`.

## Code Style

- **Match the style of the surrounding code.** Follow the naming, indentation, and comment conventions of the nearby code.
- **Do not touch code unrelated to the requested change.** Do not reformat or modify unrelated lines (keep diffs minimal).

## Verification

- **Verify code after writing it.** Run tests, or actually run it and check the result.
- **Mark anything unverified as "unverified".** Do not say "done" or "fixed" without confirming behavior.

## Destructive / Irreversible Operations

Always confirm with the user before performing the following.

- **Deleting, moving, or renaming files or directories.**
- **Operations that rewrite git history.** `git reset --hard`, `git rebase`, force push (`git push --force`), etc.

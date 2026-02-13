# Create Pull Request

Safe PR creation workflow. Follow these steps exactly.

## Pre-flight

1. Run `git branch --show-current` to confirm you are NOT on `main`. If on main, STOP and tell the user to create a feature branch first.
2. Run `gh pr list` to check for existing open PRs on this branch.
3. Run `git status` to see all staged, unstaged, and untracked changes.
4. Run `git diff` to review what will be committed.

## Stage and Commit

5. Stage relevant files by name (never `git add -A` or `git add .` unless the user explicitly asks).
6. Run `git log --oneline -5` to match the repo's commit message style.
7. Create a commit with a descriptive message following the repo's style. End with `Co-Authored-By: Claude Opus 4.6 <noreply@anthropic.com>`.

## Push and Create PR

8. Push the branch: `git push -u origin <branch-name>`.
9. Create the PR with `gh pr create --title "..." --body "..."`. Use this body format:

```
## Summary
<1-3 bullet points>

## Test plan
- [ ] <verification steps>

Generated with [Claude Code](https://claude.com/claude-code)
```

## STOP

10. Show the user the PR link.
11. **DO NOT merge the PR.** Do not run `gh pr merge`. Do not push to main.
12. Wait for the user to explicitly tell you to merge before taking any further action.

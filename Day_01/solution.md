# Solution: Git Day 01

Run these commands in order:

1. git init
2. touch README.md
3. git status         ← check README.md is untracked
4. git add README.md
5. git status         ← check README.md is staged
6. git commit -m "Initial commit: add README"
7. git log --oneline  ← verify your commit appears

Key concept: git add moves files to the staging area.
git commit saves the staged snapshot permanently.
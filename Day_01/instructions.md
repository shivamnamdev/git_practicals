# Git Day 01: Init, Add, Commit

## What You Will Learn
How Git tracks your work using 3 simple steps: init → add → commit.

---

## Task 1: Initialize a repository
Run this command to start tracking a folder with Git:

```
git init

```


Expected: You see "Initialized empty Git repository"

---

## Task 2: Create a file and check status

```
touch README.md
git status
```

Expected: README.md appears under "untracked files"

---

## Task 3: Stage the file


```
git add README.md
git status
```

Expected: README.md moves to "Changes to be committed"

---

## Task 4: Make your first commit

```
git commit -m "Initial commit: add README"
git log --oneline
```

Expected: You see one commit in the log
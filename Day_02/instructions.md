# Assignment file: instructions.md

# Git Day 02: Diff, Log, Show & Commit Comparison

## What You Will Learn

In this assignment, you will learn how to inspect changes in Git.

You will practice:

* Checking unstaged changes using `git diff`
* Checking staged changes using `git diff --staged`
* Creating multiple commits
* Viewing commit history using `git log` and `git log --oneline`
* Comparing two commits using `git diff commit1 commit2`
* Inspecting a specific commit using `git show`
* Viewing old file content using `git show commit_id:file_name`

---

## Task 1: Initialize a new repository

Create a new folder and initialize Git.

```
mkdir git-day-02
cd git-day-02
git init
```

Expected: You see "Initialized empty Git repository"

---

## Task 2: Create the first Python file

Create a file named `python-pattern.py`.

Add this content:

```
for i in range(1, 4):
    print("*" * i)
```

Run the file:

```
python3 python-pattern.py
```

Expected output:

```
*
**
***
```

Now check status:

```
git status
```

Expected: `python-pattern.py` appears under "untracked files"

---

## Task 3: Stage and commit the first version

Stage the file:

```
git add python-pattern.py
git status
```

Expected: `python-pattern.py` appears under "Changes to be committed"

Commit the file:

```
git commit -m "Added initial python pattern"
```

Check history:

```
git log
git log --oneline
```

Expected: You see one commit in the history.

---

## Task 4: Modify the file and check unstaged diff

Now update `python-pattern.py` with this content:

```
for i in range(1, 6):
    print("*" * i)
```

Run the file:

```
python3 python-pattern.py
```

Expected output:

```
*
**
***
****
*****
```

Now check the difference:

```
git diff
```

Expected: Git shows the difference between the last committed version and your current working directory changes.

Important concept:

`git diff` shows changes that are modified but not staged yet.

---

## Task 5: Stage the file and check staged diff

Stage the file:

```
git add python-pattern.py
```

Now check normal diff:

```
git diff
```

Expected: No output, because the change is already staged.

Now check staged diff:

```
git diff --staged
```

Expected: Git shows the staged changes.

Important concept:

`git diff --staged` shows changes that are added to staging area but not committed yet.

---

## Task 6: Commit the updated pattern

Commit the staged change:

```
git commit -m "Updated the python pattern"
```

Check history:

```
git log --oneline
```

Expected: You see two commits.

---

## Task 7: Fix the pattern and commit again

Now update `python-pattern.py` with this content:

```
for i in range(1, 6):
    print(" " * (5 - i) + "*" * i)
```

Run the file:

```
python3 python-pattern.py
```

Expected output:

```
    *
   **
  ***
 ****
*****
```

Now stage and commit:

```
git add python-pattern.py
git commit -m "Fixed the pattern"
```

Check history:

```
git log --oneline
```

Expected: You see three commits.

---

## Task 8: Create one more file and commit two files together

Create a new file named `time.py`.

Add this content:

```
from datetime import datetime

print(datetime.now().strftime("%I:%M %p"))
```

Now modify `python-pattern.py` again by adding one line at the top:

```
print("Right aligned pattern")
```

Now your `python-pattern.py` should look like this:

```
print("Right aligned pattern")

for i in range(1, 6):
    print(" " * (5 - i) + "*" * i)
```

Check status:

```
git status
```

Stage both files:

```
git add time.py
git add python-pattern.py
```

Commit both files:

```
git commit -m "Updated pattern and added time file"
```

Check history:

```
git log --oneline
```

Expected: You see at least four commits.

---

## Task 9: Compare two commits

Run:

```
git log --oneline
```

Copy any two commit IDs from your history.

Now compare them:

```
git diff commit_id_1 commit_id_2
```

Example:

```
git diff abc1234 def5678
```

Expected: Git shows the difference between those two commits.

Important:

The order of commit IDs matters.

This:

```
git diff old_commit new_commit
```

shows what changed from old to new.

This:

```
git diff new_commit old_commit
```

shows the reverse difference.

---

## Task 10: Inspect a specific commit

Run:

```
git log --oneline
```

Copy the latest commit ID.

Now inspect it:

```
git show commit_id
```

Example:

```
git show abc1234
```

Expected: Git shows:

* Commit ID
* Author
* Date
* Commit message
* File changes

---

## Task 11: View old file content from a commit

Use this command:

```
git show commit_id:python-pattern.py
```

Example:

```
git show abc1234:python-pattern.py
```

Expected: Git shows how `python-pattern.py` looked in that specific commit.

Also try:

```
git show commit_id:time.py
```

Expected: If `time.py` existed in that commit, Git will show its content.

If it did not exist yet, Git will show an error.

---

## Final Expected Output

By the end of this assignment:

* Repository should be initialized
* `python-pattern.py` should exist
* `time.py` should exist
* At least 4 commits should exist
* `git log --oneline` should show commit history
* You should have practiced:

  * `git diff`
  * `git diff --staged`
  * `git diff commit1 commit2`
  * `git show commit_id`
  * `git show commit_id:file_name`


## Final Command Revision

```
git status
git diff
git diff --staged
git add file_name
git commit -m "message"
git log
git log --oneline
git diff commit1 commit2
git show commit_id
git show commit_id:file_name
```

---

## Key Concepts

`git diff` shows unstaged changes.

`git diff --staged` shows staged changes.

`git log` shows full commit history.

`git log --oneline` shows short commit history.

`git diff commit1 commit2` compares two commits.

`git show commit_id` shows details of one commit.

`git show commit_id:file_name` shows how a file looked in that commit.

Commit IDs are like addresses of Git checkpoints.

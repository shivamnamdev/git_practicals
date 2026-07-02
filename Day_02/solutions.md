# Solution: Git Day 02

Run these commands in order.

---

## Step 1: Create repository

```
mkdir git-day-02
cd git-day-02
git init
```

---

## Step 2: Create first version of python-pattern.py

Create `python-pattern.py` and add:

```
for i in range(1, 4):
    print("*" * i)
```

Run:

```
python3 python-pattern.py
git status
```

---

## Step 3: Stage and commit first version

```
git add python-pattern.py
git status
git commit -m "Added initial python pattern"
git log --oneline
```

---

## Step 4: Modify file and check git diff

Update `python-pattern.py`:

```
for i in range(1, 6):
    print("*" * i)
```

Run:

```
python3 python-pattern.py
git diff
```

Key concept:

`git diff` shows unstaged changes.

---

## Step 5: Stage and check git diff --staged

```
git add python-pattern.py
git diff
git diff --staged
```

Key concept:

After staging, normal `git diff` becomes empty, but `git diff --staged` shows the staged change.

---

## Step 6: Commit updated pattern

```
git commit -m "Updated the python pattern"
git log --oneline
```

---

## Step 7: Fix the pattern

Update `python-pattern.py`:

```
for i in range(1, 6):
    print(" " * (5 - i) + "*" * i)
```

Run and commit:

```
python3 python-pattern.py
git add python-pattern.py
git commit -m "Fixed the pattern"
git log --oneline
```

---

## Step 8: Add time.py and update pattern again

Create `time.py`:

```
from datetime import datetime

print(datetime.now().strftime("%I:%M %p"))
```

Update `python-pattern.py`:

```
print("Right aligned pattern")

for i in range(1, 6):
    print(" " * (5 - i) + "*" * i)
```

Now run:

```
git status
git add time.py
git add python-pattern.py
git commit -m "Updated pattern and added time file"
git log --oneline
```

---

## Step 9: Compare commits

Run:

```
git log --oneline
```

Copy two commit IDs.

Then run:

```
git diff old_commit_id new_commit_id
```

Example:

```
git diff abc1234 def5678
```

Try reverse order also:

```
git diff def5678 abc1234
```

Observe how the difference changes.

---

## Step 10: Inspect commit details

Run:

```
git show commit_id
```

Example:

```
git show abc1234
```

This shows commit details and changes.

---

## Step 11: View file content from old commit

Run:

```
git show commit_id:python-pattern.py
```

Example:

```
git show abc1234:python-pattern.py
```

Also try:

```
git show commit_id:time.py
```

If the file existed in that commit, Git will show it.

If it did not exist in that commit, Git will show an error.

---
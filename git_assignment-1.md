# Git & GitHub Assignment

For each **📸**, you must paste the terminal output or add a screenshot to this repository.

---

## Setup

Make sure you can read this file from GitHub.

Get two local clones of this GitHub repository (call them `Repo A` and `Repo B`). 
✋🏽 The rest of the assignment builds on top of this setup. Please make sure to get it right before moving on.

> **Repo A:** `C:\Users\khanm\OneDrive - Vrije Universiteit Amsterdam\Desktop\Git assignment`  
> **Repo B:** `C:\Users\khanm\OneDrive - Vrije Universiteit Amsterdam\Desktop\Repo B`

---

## Task 1: Local merge conflict

Set up a conflict entirely within Repo A: two branches with different changes on the same line, then merge them.

1. Setup: On your `main` branch, create a file named `conflict.txt`, add a line of text, and commit it.
2. Branch 1: Create and switch to branch `feature-left`. Modify that line of text, commit the change, and switch back to `main`.
3. Branch 2: From `main`, create and switch to branch `feature-right`. Modify that same line of text with a different change, and commit it.
4. The Merge: Switch back to `main`. Merge `feature-left` (this will succeed automatically), then try to merge `feature-right`.
5. The Fix: Git will flag a conflict. Open `conflict.txt`, look at the conflict markers, manually choose or combine the changes, and delete the markers. Save, stage (`git add`), and commit to finalize the merge.


### Deliverables

📸 **Conflict markers in conflict.txt:**
```
<<<<<<< HEAD
This is the LEFT branch change
=======
This is the RIGHT branch change
>>>>>>> feature-right
```

📸 **`git log --oneline` on `main` after resolving and merging:**
```
2f6c1e6 Resolve merge conflict between feature-left and feature-right
6f000b9 feature-right: modify conflict.txt
db344ad feature-left: modify conflict.txt
3f176c5 Add conflict.txt with original line
d56ba26 Initial commit: add assignment files
```

---

## Task 2: Local and remote branches

Create a branch in Repo A, make a commit on it, and check from GitHub and Repo B whether it exists. Then push it and check again from Repo B. Switch to it in Repo B and make another commit.

### Deliverables

📸 **`git branch -a` from Repo B BEFORE the push:**
```
* main
  remotes/origin/HEAD -> origin/main
  remotes/origin/main
```

📸 **`git branch -a` from Repo B AFTER fetching:**
```
* main
  remotes/origin/HEAD -> origin/main
  remotes/origin/main
  remotes/origin/task2-branch
```

📸 **`git log --oneline` from Repo B checked out on `task2-branch` with one commit:**
```
bcdb17b Repo B: add repob_work.txt on task2-branch
93dd16c Task 2: add task2.txt on task2-branch
2f6c1e6 Resolve merge conflict between feature-left and feature-right
6f000b9 feature-right: modify conflict.txt
db344ad feature-left: modify conflict.txt
3f176c5 Add conflict.txt with original line
d56ba26 Initial commit: add assignment files
```

---

## Task 3: Pull conflict

Create a merge conflict with Repo A and Repo B, with Repo A pushing first. Then try to push from Repo B. 

### Deliverables

📸 **Push rejection message from Repo B:**
```
To github.com:Moeed2/Git-Assigment.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'github.com:Moeed2/Git-Assigment.git'
hint: Updates were rejected because the remote contains work that you do not
hint: have locally. This is usually caused by another repository pushing to
hint: the same ref. If you want to integrate the remote changes, use
hint: 'git pull' before pushing again.
```

📸 **Conflict markers after pulling:**
```
<<<<<<< HEAD
Repo B conflicting change on same file
=======
Repo A changes line 1
>>>>>>> a16e148b3f64c705d15da7f3b18f34bb92e67d29
```

📸 **`git log --oneline origin/main` after resolving:**
```
a6d41e2 Resolve pull conflict in shared.txt
11c236e Repo B: add shared.txt with different content
a16e148 Repo A: add shared.txt
2f6c1e6 Resolve merge conflict between feature-left and feature-right
6f000b9 feature-right: modify conflict.txt
db344ad feature-left: modify conflict.txt
3f176c5 Add conflict.txt with original line
d56ba26 Initial commit: add assignment files
```

---

## Task 4: Don't push secrets (.gitignore)

In **Repo A**, create a file that would normally contain secrets (for example `.env`) and put some obvious fake secret values in it (API key, password, etc.).

1. Confirm Git notices it (it should show as untracked).
2. Add that filename to `.gitignore`. (create this file first if necessary)
3. Confirm Git no longer lists it as untracked.
4. Commit and push **only** the `.gitignore` change (do **not** commit or push the secret file).

### Deliverables

📸 **`git status` showing `.env` as untracked (before `.gitignore`):**
```
On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	.env

nothing added to commit but untracked files present (use "git add" to track)
```

📸 **`.gitignore` contents including ignore rule:**
```
.env
.claude/
```

📸 **`git status` after adding `.gitignore` (`.env` no longer listed):**
```
On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	.gitignore

nothing added to commit but untracked files present (use "git add" to track)
```

---

## Task 5: Setup your project repo

Now work together with your group to setup your repository for the project.
- Make sure all team members have access to the repository
- Clone the repository to any location you like
- Set up the following branches
    - `main`
    - `dev`
    - `personal/[name]` for each team member 

### Deliverables
* 📸 `git branch -a` (or a GitHub screenshot) of your project repo completely setup.

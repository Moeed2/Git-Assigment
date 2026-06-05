# Git & GitHub Assignment

## Setup

Repo A is in `Desktop/Git assignment` and Repo B is in `Desktop/Repo B`. Both clones point to the same GitHub repo.

## Task 1: Local merge conflict

Conflict markers in `conflict.txt` after trying to merge `feature-right`:

```
<<<<<<< HEAD
This is the LEFT branch change
=======
This is the RIGHT branch change
>>>>>>> feature-right
```

`git log --oneline` on main after resolving:

```
2f6c1e6 Resolve merge conflict between feature-left and feature-right
6f000b9 feature-right: modify conflict.txt
db344ad feature-left: modify conflict.txt
3f176c5 Add conflict.txt with original line
d56ba26 Initial commit: add assignment files
```

## Task 2: Local and remote branches

`git branch -a` from Repo B before the push (task2-branch not visible):

```
* main
  remotes/origin/HEAD -> origin/main
  remotes/origin/main
```

`git branch -a` from Repo B after fetching:

```
* main
  remotes/origin/HEAD -> origin/main
  remotes/origin/main
  remotes/origin/task2-branch
```

`git log --oneline` from Repo B on task2-branch after making one commit:

```
bcdb17b Repo B: add repob_work.txt on task2-branch
93dd16c Task 2: add task2.txt on task2-branch
2f6c1e6 Resolve merge conflict between feature-left and feature-right
6f000b9 feature-right: modify conflict.txt
db344ad feature-left: modify conflict.txt
3f176c5 Add conflict.txt with original line
d56ba26 Initial commit: add assignment files
```

## Task 3: Pull conflict

Push rejection from Repo B:

```
To github.com:Moeed2/Git-Assigment.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'github.com:Moeed2/Git-Assigment.git'
hint: Updates were rejected because the remote contains work that you do not
hint: have locally. This is usually caused by another repository pushing to
hint: the same ref. If you want to integrate the remote changes, use
hint: 'git pull' before pushing again.
```

Conflict markers in `shared.txt` after pulling:

```
<<<<<<< HEAD
Repo B conflicting change on same file
=======
Repo A changes line 1
>>>>>>> a16e148b3f64c705d15da7f3b18f34bb92e67d29
```

`git log --oneline origin/main` after resolving and pushing:

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

## Task 4: .gitignore

`git status` before adding `.gitignore` (`.env` is untracked):

```
On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	.env

nothing added to commit but untracked files present (use "git add" to track)
```

Contents of `.gitignore`:

```
.env
```

`git status` after adding `.gitignore` (`.env` no longer shown):

```
On branch main
Your branch is up to date with 'origin/main'.



Untracked files:
  (use "git add <file>..." to include in what will be committed)
	.gitignore

nothing added to commit but untracked files present (use "git add" to track)
```

## Task 5: 
<img width="1899" height="733" alt="image-1780669929479" src="https://github.com/user-attachments/assets/46aadadc-e28d-498a-87a8-7799885a96a6" />


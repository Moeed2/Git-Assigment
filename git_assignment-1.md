# Git & GitHub Assignment

For each **📸**, you must paste the terminal output or add a screenshot to this repository.

---

## Setup

Make sure you can read this file from GitHub.

Get two local clones of this GitHub repository (call them `Repo A` and `Repo B`). 
✋🏽 The rest of the assignment builds on top of this setup. Please make sure to get it right before moving on.

---

## Task 1: Local merge conflict

Set up a conflict entirely within Repo A: two branches with different changes on the same line, then merge them.

1. Setup: On your `main` branch, create a file named `conflict.txt`, add a line of text, and commit it.
2. Branch 1: Create and switch to branch `feature-left`. Modify that line of text, commit the change, and switch back to `main`.
3. Branch 2: From `main`, create and switch to branch `feature-right`. Modify that same line of text with a different change, and commit it.
4. The Merge: Switch back to `main`. Merge `feature-left` (this will succeed automatically), then try to merge `feature-right`.
5. The Fix: Git will flag a conflict. Open `conflict.txt`, look at the conflict markers, manually choose or combine the changes, and delete the markers. Save, stage (`git add`), and commit to finalize the merge.


### Deliverables
* 📸 The conflict markers in that particular file  
* 📸 `git log --oneline` on `main` after resolving and merging

---

## Task 2: Local and remote branches

Create a branch in Repo A, make a commit on it, and check from GitHub and Repo B whether it exists. Then push it and check again from Repo B. Switch to it in Repo B and make another commit.

### Deliverables
* 📸 `git branch -a` from Repo B **before** the push  
* 📸 `git branch -a` from Repo B **after** fetching  
* 📸 `git log --oneline` from Repo B checked out on that branch with one commit.


---

## Task 3: Pull conflict

Create a merge conflict with Repo A and Repo B, with Repo A pushing first. Then try to push from Repo B. 

### Deliverables
* 📸 The push rejection message from Repo B  
* 📸 The conflict markers after pulling  
* 📸 `git log --oneline origin/main` (or a GitHub screenshot) after resolving

---

## Task 4: Don’t push secrets (.gitignore)

In **Repo A**, create a file that would normally contain secrets (for example `.env`) and put some obvious fake secret values in it (API key, password, etc.).

1. Confirm Git notices it (it should show as untracked).
2. Add that filename to `.gitignore`. (create this file first if necessary)
3. Confirm Git no longer lists it as untracked.
4. Commit and push **only** the `.gitignore` change (do **not** commit or push the secret file).

### Deliverables
* 📸 `git status` showing the secret file as untracked (before `.gitignore`)  
* 📸 `.gitignore` contents including your ignore rule  
* 📸 `git status` after adding `.gitignore` (showing the secret file is not listed)

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



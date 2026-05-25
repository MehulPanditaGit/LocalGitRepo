# Git & GitHub Assignment Submission

This repository contains the complete, step-by-step implementation of the hands-on Git assignment tasks, ranging from basic local configuration to complex patch staging, branching strategies, conflict resolution, and fork workflows.

---

## 📋 Table of Contents
1. [Initialize a Local Git Repository](#1-initialize-a-local-git-repository)
2. [Remote Repository Operations](#2-remote-repository-operations)
3. [Branching and Pull Request](#3-branching-and-pull-request)
4. [Local Git Operations](#4-local-git-operations)
5. [Branching Merging and Cleanup](#5-branching-merging-and-cleanup)
6. [Fork Operations](#6-fork-operations)
7. [Complex Staging, Stash, and History Manipulation](#7-complex-staging-stash-and-history-manipulation)
8. [Submission Details & Links](#8-submission-details--links)

---

## 1. Initialize a Local Git Repository
* **Repository Init**: Initialised empty repository using `git init`.
* **Initial Commit**: Created `initial.txt`, staged with `git add initial.txt`, and committed to `main`.
* **Staging and Unstaging Mechanics**:
  * Staged `temp.txt` -> Unstaged via `git restore --staged temp.txt`.
  * Modified `temp.txt` -> Staged again -> Unstaged using legacy `git reset HEAD temp.txt`.

## 2. Remote Repository Operations
* **Remote Linking**: Tied local tracking to GitHub using `git remote add origin`.
* **Remote Editing & Synchronization**: 
  * Appended new line directly via GitHub interface.
  * Pulled changes locally using `git pull origin main` to maintain synchronization.
* **Selective Target Commits**:
  * Staged `file1.txt` and `file2.txt`.
  * Isolated and dropped `file2.txt` from index using `git reset HEAD file2.txt`.
  * Committed and pushed `file1.txt`.

## 3. Branching and Pull Request
* **Remote Provisioning**: Created branch `g1` on GitHub Web.
* **Tracking & Delivery**:
  * Fetched locally via `git fetch origin` and checked out with `git checkout g1`.
  * Created, committed, and pushed `g1_file.txt`.
* **Pull Request**: Submitted a PR from `g1` to `main` on GitHub and merged cleanly.
* **PR Link**: *[Insert your merged g1 -> main PR Link here]*

## 4. Local Git Operations
* **Upstream Sync**: Synchronized local tracking state using `git fetch origin` and `git merge origin/main`.
* **Reset Operations**:
  * **Soft Reset**: Committed changes to `initial.txt`, performed `git reset --soft HEAD~1`, and verified files remained staged in working tree.
  * **Patch Selection**: Used `git add -p` to stage specific file hunks interactively.
  * **Hard Reset**: Evaluated data loss workflow by executing `git reset --hard HEAD~1`, showing complete removal of unstaged work through `git status`.
* **Inspection Commands**:
  * Evaluated file structural drift across references using `git diff main g1`.
  * Enumerated explicit tracking items with `git ls-files` and `git status`.
* **Branch Tree Proliferation**:
  * `main` ──> `b1` *(Modified initial.txt)*
  * `b1` ──> `b2` *(Added b2_file.txt)*
  * `b2` ──> `b3` *(Modified b2_file.txt)*
* **Mixed Index Clear**: Staged broad workspace changes on `b3`, then cleared index without touching disk files via `git reset --mixed HEAD`.

## 5. Branch Merging and Cleanup
* **Sequential Integration**: Merged downstream branches up the lineage chain (`b3` ➔ `b2` ➔ `b1` ➔ `main`).
* **Deliberate Merge Conflict**: 
  * Altered the exact same sentence lines on `b2` and `b3`.
  * Threw conflict flag on `git merge`, manually stripped layout markers (`<<<<<<<`, `=======`, `>>>>>>>`), kept both inputs, and ran final merge commit.
* **Tree Optimization & Deletion**:
  * Cleaned up local traces using force/normal flags: `git branch -d b1 b2 b3`.
  * Cleared GitHub remote branch reference index using `git push origin --delete g1`.

## 6. Fork Operations
* **Fork Provisioning**: Created an independent copy tracking instance (`grafify`).
* **Workspace Cloning**: Cloned the isolated instance downstream to a separate working workspace directory.
* **Upstream Contribution**: Added `forked.txt`, saved changes to local master reference index, and pushed upstream to target fork reference space.
* **Fork PR Link**: *[Insert your Fork PR Link here]*

## 7. Complex Staging, Stash, and History Manipulation
* **Workspace Setup**: Modified `initial.txt`, `b2_file.txt`, and introduced a new untracked `challenge.txt`.
* **Staging Adjustments**:
  * Bulk staged using `git add .`.
  * Isolated and dropped `challenge.txt` using `git reset HEAD challenge.txt`.
  * Parsed and split remaining modified file sections using interactive hunk selections: `git add -p initial.txt`.
* **Stash Manipulation**: Committed the staged components, then safely shelved remaining work out of sight using `git stash -u`.
* **Stash Collision Generation**: Modified identical working files inside active branch space, called `git stash pop`, manually resolved the expected structural block collision, and finalized history tracking state.
* **File System Operations**: Executed target workspace cleanups using `git rm`, and performed explicit history rollbacks safely without destroying log timelines using `git revert`.

---

## 8. Submission Details & Links

* **Main Repository URL**: [https://github.com](https://github.com)
* **Forked Repository URL**: [https://github.com](https://github.com)

### Pull Request Summaries
1. **Feature Branch PR (`g1` to `main`)**: [Click here to view branch merge PR]
2. **Cross-Repository Fork PR (`grafify` to upstream)**: [Click here to view fork contribution PR]

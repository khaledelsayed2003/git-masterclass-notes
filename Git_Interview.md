# 🚀 Git & GitHub – 100 Interview Questions & Answers (Complete Guide)

> A practical, internals-aware guide for **students, developers, and interview preparation**
> Covers **Git fundamentals, internals, branching, undoing, remotes, collaboration, and GitHub workflows**

---

## 📘 Fundamentals

### 1. What is a Version Control System (VCS)?

A VCS tracks changes in files over time, allowing you to save versions, revert changes, and collaborate safely.

---

### 2. What is Git?

Git is a **distributed version control system** that tracks changes using snapshots and stores the full history locally.

---

### 3. What is GitHub?

GitHub is a **remote hosting and collaboration platform** for Git repositories.

---

### 4. Git vs GitHub?

* **Git** → local version control tool
* **GitHub** → online platform to host and share Git repositories

---

### 5. Types of Version Control Systems?

* **Local VCS** – versions stored locally
* **Centralized VCS** – one central server
* **Distributed VCS** – full copy per developer (Git)

---

### 6. Why is Git distributed?

Each developer has the **full history**, can work offline, and sync later.

---

### 7. What is a repository?

A repository is a project folder managed by Git, containing a hidden `.git` directory with full history.

---

### 8. What does `git init` do?

Creates a new local Git repository by adding a `.git` folder.

---

### 9. What is inside `.git`?

Git objects, refs, HEAD, index, configuration, and history.

---

### 10. Git is best described as what?

A **database of snapshots**, not a set of files.

---

## 🧠 Git Internals

### 11. How does Git detect file changes?

By recalculating a **SHA-1 hash** based on file content, size, and type.

---

### 12. What is a Git SHA?

A 40-character hexadecimal hash (160 bits) uniquely identifying Git objects.

---

### 13. What are Git objects?

* **Blob**
* **Tree**
* **Commit**
* **Tag**

---

### 14. What is a Blob?

Stores **file content only** (no filename or path).

---

### 15. What is a Tree?

Represents a directory structure and maps filenames to blob hashes.

---

### 16. What is a Commit?

A snapshot pointing to a tree and containing metadata (author, message, parent).

---

### 17. What objects are created in every commit?

* 1 Commit
* 1+ Trees
* 0+ Blobs (reused if unchanged)

---

### 18. Why are blobs reused?

Same content → same SHA → no duplication.

---

### 19. What is a Tag?

A fixed pointer to a commit, usually for releases.

---

### 20. Branch vs Tag?

* Branch → moves forward
* Tag → fixed reference

---

## 🌳 Three-Tree Architecture

### 21. What are Git’s three trees?

* **Working Directory**
* **Staging Area (Index)**
* **Repository**

---

### 22. What does `git add` do?

Moves changes from Working Directory to Staging Area.

---

### 23. What does `git commit` do?

Creates a snapshot of staged changes in the repository.

---

### 24. What does `git status` show?

State of files: untracked, modified, staged.

---

### 25. What does `git status -s` show?

Short status:

* Red M → modified (not staged)
* Green M → staged

---

## 🔍 Inspecting Changes

### 26. What does `git diff` show?

Differences between **Working Directory** and **Staging Area**.

---

### 27. What does `git diff --staged` show?

Differences between **Staging Area** and **Last Commit**.

---

### 28. How to compare two commits?

```bash
git diff A..B
```

Shows changes from A → B.

---

### 29. What does `git show` do?

Displays a commit and its exact changes.

---

### 30. How to view commit history?

```bash
git log
git log --oneline
```

---

## 🔁 Undoing Changes

### 31. Undo working directory changes?

```bash
git restore <file>
```

---

### 32. Unstage a file?

```bash
git restore --staged <file>
```

---

### 33. Remove a tracked file without deleting it?

```bash
git rm --cached <file>
```

---

### 34. Remove last commit locally?

```bash
git reset --hard HEAD~1
```

---

### 35. Remove commit from GitHub?

```bash
git push --force-with-lease
```

⚠️ Rewrites history.

---

### 36. Safe alternative to delete a commit?

```bash
git revert <commit>
```

---

### 37. reset vs revert?

* **reset** → rewrites history
* **revert** → safe for shared repos

---

### 38. Recover a deleted commit?

```bash
git reflog
git reset --hard <sha>
```

---

### 39. Amend last commit message?

```bash
git commit --amend -m "new message"
```

---

### 40. Commit and add in one command?

```bash
git commit -am "message"
```

---

## 🌿 Branching

### 41. What is HEAD?

A pointer showing the current branch and commit.

---

### 42. What is a branch?

A movable pointer to a commit for parallel development.

---

### 43. Create a branch?

```bash
git branch feature
```

---

### 44. Switch branches?

```bash
git switch feature
```

---

### 45. Create & switch?

```bash
git switch -c feature
```

---

### 46. What files do you see in your editor?

The commit that HEAD points to.

---

### 47. What is fast-forward merge?

Git moves the branch pointer forward without creating a merge commit.

---

### 48. What is divergent history?

Both branches have new commits after branching.

---

### 49. What is a 3-way merge?

Uses:

* common ancestor
* branch A
* branch B
  Creates a new merge commit.

---

### 50. Delete a merged branch?

```bash
git branch -d feature
```

---

## 🌐 Remotes & Collaboration

### 51. What are remotes?

External repositories linked to your local repo.

---

### 52. What is origin?

Default name for the remote you cloned from.

---

### 53. Show remotes?

```bash
git remote -v
```

---

### 54. What does `git push` do?

Uploads commits to a remote repository.

---

### 55. What does `git pull` do?

Fetches and merges updates.

---

### 56. What does `git fetch` do?

Downloads updates **without merging**.

---

### 57. pull vs fetch?

* pull = fetch + merge
* fetch = review first

---

### 58. View remote branches?

```bash
git branch -r
```

---

### 59. Push a new branch?

```bash
git push -u origin branch_name
```

---

### 60. What does `-u` mean?

Sets upstream tracking branch.

---

## 🤝 GitHub Workflows

### 61. Clone vs Download ZIP?

* Clone → full history
* ZIP → snapshot only

---

### 62. What is fork?

A GitHub copy of a repository under your account.

---

### 63. Why fork?

No write access to original repo.

---

### 64. origin vs upstream?

* origin → your fork
* upstream → original repo

---

### 65. Keep fork updated?

```bash
git fetch upstream
git merge upstream/main
```

---

### 66. What is a Pull Request (PR)?

A request to merge your branch into another repo.

---

### 67. Should you work on main?

❌ No. Always use feature branches.

---

### 68. Why commit before merging?

Git merges **commits**, not uncommitted changes.

---

### 69. Test a friend’s branch locally?

```bash
git fetch origin
git checkout dev
git pull origin dev
```

---

### 70. Rename master to main?

```bash
git branch -m master main
git push -u origin main
git push origin --delete master
```

---

## ⚙️ Configuration

### 71. Set username?

```bash
git config --global user.name "Your Name"
```

---

### 72. Set email?

```bash
git config --global user.email "you@email.com"
```

---

### 73. Check config?

```bash
git config --list
```

---

### 74. List tracked files?

```bash
git ls-files
```

---

### 75. Remove Git entirely?

```bash
rm .git -Recurse -Force
```

---

## 📌 Advanced Concepts

### 76. Does cloning count as contribution?

❌ No.

---

### 77. What counts as GitHub contribution?

* Commits
* Creating a repository

---

### 78. When is contribution time counted?

Commit time, not push time.

---

### 79. Can you undo without deleting history?

Yes, using `git revert`.

---

### 80. What is reflog?

A local history of HEAD movements.

---

### 81. Are commits immutable?

Yes. New commits reference old ones.

---

### 82. Why is Git secure?

SHA-1 hashes form a linked history.

---

### 83. What happens if server dies?

Nothing — Git is distributed.

---

### 84. Why Git is fast?

Local operations + object reuse.

---

### 85. Can Git work offline?

Yes.

---

### 86. Does Git store diffs?

No — full snapshots.

---

### 87. Why staging area exists?

For controlled commits.

---

### 88. Can one commit have multiple parents?

Yes — merge commits.

---

### 89. What is detached HEAD?

HEAD pointing directly to a commit.

---

### 90. How to tag a release?

```bash
git tag -a v1.0 -m "release"
```

---

## 🧠 Final Interview-Level Knowledge

### 91. Git = database of?

Objects + pointers.

---

### 92. Most dangerous command?

```bash
git reset --hard
```

---

### 93. Safest undo command?

```bash
git revert
```

---

### 94. Best practice before pull?

```bash
git fetch
```

---

### 95. Best practice before merge?

Commit first.

---

### 96. Can branches be deleted safely?

Yes, after merge.

---

### 97. Why feature branches?

Isolation + safety.

---

### 98. Why PRs matter?

Code review + collaboration.

---

### 99. What makes Git interview-ready?

Understanding internals, not commands.

---

### 100. One-line Git definition?

**Git is a distributed database of snapshots connected by cryptographic pointers.**

---


# Git & GitHub – Interview Questions & Answers (Complete Guide)

## 1. What is a Version Control System (VCS)?

A Version Control System tracks changes in source code over time.
It allows developers to save versions, revert changes, and collaborate safely.

---

## 2. What is Git?

Git is a **distributed version control system** that stores the complete history of a project locally and tracks changes using snapshots.

---

## 3. What is GitHub?

GitHub is a **hosting and collaboration platform** for Git repositories.
It provides remote storage, pull requests, issues, and team collaboration.

---

## 4. Difference between Git and GitHub?

- **Git** → local tool for version control
- **GitHub** → remote platform to host and share Git repositories

---

## 5. What are the types of VCS?

- **Local VCS** – versions stored locally
- **Centralized VCS** – single central server
- **Distributed VCS** – full copy for each user (Git)

---

## 6. How does Git detect file changes?

Git calculates a **SHA-1 hash** based on file content, type, and size.
If the hash changes, Git knows the file changed.

---

## 7. What is a Git SHA?

A Git SHA is a 40-character hexadecimal hash (160 bits) that uniquely identifies objects (commits, trees, blobs).

---

## 8. Explain Git’s three-tree architecture.

1. **Working Directory** – your actual files
2. **Staging Area (Index)** – files prepared for commit
3. **Repository** – committed snapshots

---

## 9. What happens internally when you commit?

Git creates:

- **Blob** → file content
- **Tree** → directory structure
- **Commit** → metadata + pointer to tree

---

## 10. What is a Blob in Git?

A Blob stores **file content only**, not the filename or path.

---

## 11. What is a Tree in Git?

A Tree represents a directory and maps filenames to blob hashes.

---

## 12. What is a Commit in Git?

A Commit is a snapshot that points to a tree and stores metadata (author, message, parent, date).

---

## 13. What is a Repository?

A repository is a project folder managed by Git, containing files and a hidden `.git` directory with all history.

---

## 14. What is HEAD?

HEAD is a pointer that shows **which branch and commit you are currently on**.

---

## 15. What is a Branch?

A branch is a **movable pointer** to a commit, allowing parallel development.

---

## 16. Difference between branch and tag?

- **Branch** → moves forward with new commits
- **Tag** → fixed pointer used to mark releases

---

## 17. What is `git status` used for?

Shows the current state of files (untracked, modified, staged).

---

## 18. What does `git add` do?

Moves changes from the working directory to the staging area.

---

## 19. What does `git commit` do?

Creates a snapshot of staged changes in the local repository.

---

## 20. What is `git diff`?

Shows differences between:

- Working Directory and Staging Area

---

## 21. What is `git diff --staged`?

Shows differences between:

- Staging Area and Last Commit

---

## 22. How do you undo changes in the working directory?

```bash
git restore <file>
```

---

## 23. How do you unstage a file?

```bash
git restore --staged <file>
```

---

## 24. How do you remove a tracked file without deleting it?

```bash
git rm --cached <file>
```

---

## 25. How do you remove the last commit locally?

```bash
git reset --hard HEAD~1
```

---

## 26. How do you remove a commit from GitHub?

```bash
git push --force-with-lease
```

⚠️ Rewrites history — use carefully.

---

## 27. How do you recover a deleted commit?

```bash
git reflog
git reset --hard <sha>
```

---

## 28. What is `git revert`?

Creates a **new commit** that undoes a previous commit **without rewriting history**.

---

## 29. Difference between `git reset` and `git revert`?

- `reset` → rewrites history
- `revert` → safe for shared repos

---

## 30. What is `git show`?

Displays commit details and the exact changes it introduced.

---

## 31. What is fast-forward merge?

When the target branch has no new commits, Git simply moves the pointer forward.

---

## 32. What is divergent history?

When two branches both have new commits after branching.

---

## 33. What is a 3-way merge?

A merge that uses:

- Common ancestor
- Latest commit on each branch
  Creates a new merge commit.

---

## 34. How do you create and switch to a branch?

```bash
git switch -c feature
```

---

## 35. How do you merge a branch?

```bash
git switch main
git merge feature
```

---

## 36. How do you delete a merged branch?

```bash
git branch -d feature
```

---

## 37. What are remotes in Git?

Remote repositories are external versions of your repo (e.g. GitHub).

---

## 38. What is `origin`?

Default name for the remote repository you cloned from.

---

## 39. What is `git fetch`?

Downloads updates **without changing your working directory**.

---

## 40. What is `git pull`?

Fetches and merges updates immediately.

```bash
git pull = git fetch + git merge
```

---

## 41. When should you prefer fetch over pull?

When working in teams and you want to **review changes before merging**.

---

## 42. How do you see remote branches?

```bash
git branch -r
```

---

## 43. How do you push a new branch to GitHub?

```bash
git push -u origin branch_name
```

---

## 44. What does `-u` mean?

Sets an **upstream tracking branch**.

---

## 45. How do you test a friend’s branch locally?

```bash
git fetch origin
git checkout development
git pull origin development
```

---

## 46. Why must you commit before merging?

Because Git merges **commits**, not uncommitted changes.

---

## 47. How do you rename `master` to `main`?

```bash
git branch -m master main
git push -u origin main
git push origin --delete master
```

---

## 48. How are GitHub contributions counted?

- Each commit = one contribution
- Commit date matters, not push date

---

## 49. Does cloning count as contribution?

No.
Creating a repository **does** count.

---

## 50. Clone vs Download ZIP?

- **Clone** → full Git history + collaboration
- **ZIP** → one-time snapshot, no Git

---

## 51. One-line summary of Git?

**Git is a distributed database of snapshots connected by pointers.**

---

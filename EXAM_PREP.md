# Git Exam Preparation Guide

Use this guide to review key Git concepts and commands covered in the Introduction to Git exercise.

---

## 1. What is Version Control?

Version control systems help developers manage changes to code over time. Common problems they solve:

- **Backup and Recovery** – Never lose work again.
- **Sandboxed Experimentation** – Try ideas without breaking what works.
- **Parallel Development** – Multiple people (or features) can be worked on at the same time.
- **Collaboration** – Share and merge changes across a team.

**Git** is a _distributed_ version control system — every developer has a full copy of the project history locally.

---

## 2. The Git Workflow

```
Working Directory  →  (git add)  →  Staging Area  →  (git commit)  →  Repository
```

| Area | Description |
|---|---|
| Working Directory | Files you are actively editing. |
| Staging Area (Index) | A holding area for changes you plan to commit. |
| Repository | The permanent history of all committed changes. |

---

## 3. Essential Git Commands

### Identity & Configuration
```bash
git config --global user.name "First Last"
git config --global user.email "me@example.com"
git config --global --list
```

### Starting a Repository
```bash
git init          # Initialize a new repository in the current folder
git status        # View the state of your working directory and staging area
```

### Staging and Committing
```bash
git add <file>    # Stage a specific file
git add src/*     # Stage all files in a directory
git commit -m "Your commit message"   # Save staged changes to history
```

### Viewing History
```bash
git log                      # Detailed commit history
git log --oneline            # One commit per line (compact)
git log --graph --oneline    # Visual graph of commits and branches
git log --all --graph --oneline  # Show all branches in the graph
```

### Comparing Changes
```bash
git diff <file>           # Changes between working directory and staging area
git diff --staged <file>  # Changes between staging area and last commit
git diff HEAD~1           # Changes between current and previous commit
```

### Navigating History
```bash
git checkout <commit-id>  # Move to a specific commit (detached HEAD)
git checkout main         # Return to the latest commit on main
```

### Branches
```bash
git branch my-feature          # Create a new branch
git checkout my-feature        # Switch to a branch
git branch --list              # List all branches
git merge my-feature           # Merge a branch into the current branch
git merge --no-ff my-feature -m "msg"  # Merge without fast-forwarding
git branch --delete my-feature # Delete a branch label (not the history)
```

---

## 4. Understanding Git History

Each commit contains:
- **Unique hash ID** – A unique identifier (e.g., `a3f9c12`).
- **Parent commit** – Reference to the previous commit, forming a chain.
- **Author information** – Who made the changes.
- **Timestamp** – When the commit was created.
- **Commit message** – A description of what changed.

**HEAD** is a special pointer that indicates your current position in the history.

---

## 5. Understanding Diffs

Git uses `+` and `-` symbols to show changes:

```diff
+ This line was added
- This line was removed
```

---

## 6. Understanding Branches

| Concept | Description |
|---|---|
| `main` branch | The primary, trusted version of the project. |
| Feature branch | An isolated copy to develop without affecting `main`. |
| Merging | Combining changes from one branch into another. |

### Merge Strategies

| Strategy | Description |
|---|---|
| **Fast-forward** | Moves commits directly onto the parent branch (clean history). |
| **Merge commit** | Creates a new commit to record the merge (preserves branch in history). |
| **Squash merge** | Collapses branch commits into a single new commit. |

---

## 7. Collaboration Concepts

| Term | Definition |
|---|---|
| **Clone** | Copy a remote repository to your local machine. |
| **Push** | Upload local commits to a remote repository. |
| **Pull** | Download and integrate changes from a remote repository. |
| **Pull Request** | A request for others to review and merge your changes. |

---

## 8. Quick Reference Cheat Sheet

| Task | Command |
|---|---|
| Set name | `git config --global user.name "Name"` |
| Set email | `git config --global user.email "email"` |
| Initialize repo | `git init` |
| Check status | `git status` |
| Stage file | `git add <file>` |
| Commit | `git commit -m "message"` |
| View history | `git log --oneline` |
| View diff | `git diff <file>` |
| Create branch | `git branch <name>` |
| Switch branch | `git checkout <name>` |
| Merge branch | `git merge <name>` |
| Delete branch | `git branch --delete <name>` |

---

## 9. Tips for the Exam

- **Commit messages matter** – Write clear, descriptive messages. They help you and your team understand the history.
- **Commit early, commit often** – Small, focused commits are easier to review and revert.
- **Use branches** – Never experiment directly on `main`.
- **`git status` is your friend** – Check it before and after every operation.
- **Know the three areas**: working directory, staging area, and repository.
- **`HEAD`** always points to your current location in history.
- **Distributed** means every developer has the full history — no single point of failure.

---

*Good luck on your exam! 🎓*

# git status

> Display the current state of the working directory and staging area.

---

# Table of Contents

- Overview
- Purpose
- Syntax
- Common Options
- How `git status` Works
- Understanding Git States
- Examples
- Real-World DevOps Use Cases
- Best Practices
- Common Mistakes
- Interview Questions
- Summary

---

# Overview

The `git status` command displays the current state of your Git repository.

It tells you:

- Which branch you're currently on.
- Which files have been modified.
- Which files are staged for commit.
- Which files are untracked.
- Whether your branch is ahead of, behind, or synchronized with the remote repository.

Unlike many Git commands, `git status` **does not modify anything**. It only reports the repository's current state.

It is one of the safest and most frequently used Git commands.

---

# Purpose

The `git status` command is used to:

- Check the current repository status.
- View modified files.
- View staged files.
- View untracked files.
- Verify changes before committing.
- Confirm a clean working tree.

---

# Syntax

Basic usage:

```bash
git status
```

Short format:

```bash
git status --short
```

Display branch information:

```bash
git status --branch
```

---

# Common Options

| Command | Description |
|----------|-------------|
| `git status` | Display complete repository status |
| `git status --short` | Display compact output |
| `git status -s` | Short form of `--short` |
| `git status --branch` | Show branch information |

---

# How `git status` Works

Git compares three areas:

```
Working Directory

↓

Staging Area

↓

Local Repository
```

When you run:

```bash
git status
```

Git compares:

1. Working Directory ↔ Staging Area
2. Staging Area ↔ Last Commit (HEAD)

Based on these comparisons, Git determines which files are:

- Modified
- Staged
- Deleted
- Untracked

---

# Understanding Git States

## Untracked

Git sees the file for the first time.

Example:

```
notes.txt
```

Output:

```
Untracked files:

notes.txt
```

Git is **not** tracking this file yet.

---

## Modified

Git is already tracking the file, but it has changed since the last commit.

Example:

```
README.md
```

Output:

```
Changes not staged for commit
```

---

## Staged

The file has been added to the Staging Area using:

```bash
git add
```

Output:

```
Changes to be committed
```

The file is now ready for the next commit.

---

## Clean Working Tree

Everything has been committed.

Output:

```
nothing to commit, working tree clean
```

This is the ideal state before switching branches or pulling new changes.

---

# Examples

## Example 1

Check repository status.

```bash
git status
```

Output:

```
On branch main

nothing to commit, working tree clean
```

---

## Example 2

New file.

Create:

```bash
touch app.py
```

Run:

```bash
git status
```

Output:

```
Untracked files:

app.py
```

---

## Example 3

Modified file.

Modify:

```
README.md
```

Run:

```bash
git status
```

Output:

```
Changes not staged for commit:

modified: README.md
```

---

## Example 4

After staging.

```bash
git add README.md

git status
```

Output:

```
Changes to be committed:

modified: README.md
```

---

## Example 5

Short output.

```bash
git status --short
```

Example:

```
M README.md

A Dockerfile

?? notes.txt
```

Meaning:

| Symbol | Meaning |
|----------|---------|
| `M` | Modified |
| `A` | Added |
| `D` | Deleted |
| `R` | Renamed |
| `??` | Untracked |

---

# How to Read `git status --short`

The output contains two columns:

```
XY filename
```

- **First column (X):** Status in the **Staging Area**
- **Second column (Y):** Status in the **Working Directory**

Example:

```
M  README.md
```

The file is staged.

Example:

```
 M README.md
```

The file is modified but not staged.

Example:

```
MM README.md
```

The file has staged changes and additional unstaged changes.

---

# Real-World DevOps Use Cases

## Before Deployment

Before pushing Kubernetes manifests:

```bash
git status
```

Verify that only intended files are staged.

---

## Before Switching Branches

Always check:

```bash
git status
```

to avoid leaving unfinished work behind.

---

## Before Pulling Changes

A DevOps engineer runs:

```bash
git status
```

If the working tree isn't clean, they commit or stash changes before pulling updates from the remote repository.

---

## CI/CD Development

Before committing a GitHub Actions workflow:

```bash
git status
```

Ensure only the workflow file is staged.

---

# Best Practices

- Run `git status` before every commit.
- Run `git status` before switching branches.
- Run `git status` before pulling remote changes.
- Review staged files carefully.
- Keep the working tree clean whenever possible.

---

# Common Mistakes

## Forgetting to Check Status

Running:

```bash
git commit
```

without checking `git status` may result in:

- Missing files
- Extra files
- Unintended commits

---

## Ignoring Untracked Files

Developers sometimes forget to stage newly created files.

Example:

```
?? app.py
```

Git will not include this file until:

```bash
git add app.py
```

---

## Assuming Everything is Committed

Seeing:

```
modified: README.md
```

does **not** mean the changes will be committed.

Only staged files are committed.

---

# Interview Questions

### What is the purpose of `git status`?

**Answer**

It displays the current state of the repository, including modified, staged, untracked, and committed files.

---

### Does `git status` modify the repository?

**Answer**

No.

It is a read-only command that only displays information.

---

### What does "working tree clean" mean?

**Answer**

There are no uncommitted changes in the Working Directory or Staging Area.

---

### What does `??` mean in `git status --short`?

**Answer**

The file is untracked.

---

### Why should you run `git status` before committing?

**Answer**

To verify that the correct files are staged and no unintended changes are included in the commit.

---

# Summary

The `git status` command provides a snapshot of your repository's current state by comparing the Working Directory, Staging Area, and the latest commit.

It is one of the most important Git commands because it helps you understand exactly what will be committed before creating a new snapshot.

Developing the habit of running `git status` frequently leads to cleaner commits, fewer mistakes, and a more reliable Git workflow.

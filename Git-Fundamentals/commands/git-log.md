# git log

> Display the commit history of a Git repository.

---

# Table of Contents

- Overview
- Purpose
- Syntax
- Common Options
- How `git log` Works
- Internal Working
- Examples
- Real-World DevOps Use Cases
- Best Practices
- Common Mistakes
- Interview Questions
- Summary

---

# Overview

The `git log` command displays the history of commits in a Git repository.

Every time you create a commit using `git commit`, Git records it in the repository's history. The `git log` command allows you to browse that history, inspect previous commits, identify authors, review changes, and understand how the project has evolved over time.

It is one of the most frequently used commands for debugging, auditing, and reviewing project history.

---

# Purpose

The `git log` command is used to:

- View commit history.
- Identify who made changes.
- View commit messages.
- Find commit IDs (SHA hashes).
- Review project evolution.
- Debug issues by tracing changes.
- Locate commits for reset, revert, cherry-pick, or checkout.

---

# Syntax

Display complete commit history:

```bash
git log
```

Display compact history:

```bash
git log --oneline
```

Display history with a graph:

```bash
git log --graph
```

Display decorated history:

```bash
git log --decorate
```

Display all branches:

```bash
git log --all
```

Combine multiple options:

```bash
git log --graph --decorate --oneline --all
```

---

# Common Options

| Command | Description |
|----------|-------------|
| `git log` | Display complete commit history |
| `git log --oneline` | Display compact commit history |
| `git log --graph` | Show branch and merge graph |
| `git log --decorate` | Display branch and tag names |
| `git log --all` | Show commits from all branches |
| `git log -n 5` | Show the last 5 commits |
| `git log --author="John"` | Show commits by a specific author |
| `git log --since="7 days ago"` | Show recent commits |
| `git log --stat` | Display files changed in each commit |

---

# How `git log` Works

Every commit points to its parent commit.

Example:

```
Commit A

↓

Commit B

↓

Commit C (HEAD)
```

Running:

```bash
git log
```

starts at the current commit (`HEAD`) and walks backwards through the commit history until the first commit.

---

# Internal Working

Git stores commit objects inside the `.git/objects` directory.

Each commit contains:

- Commit ID
- Parent commit
- Author
- Email
- Date
- Commit message
- Snapshot reference

Example:

```
Commit C

↓

Parent → Commit B

↓

Parent → Commit A
```

When you run:

```bash
git log
```

Git follows these parent references to reconstruct the project's history.

---

# Examples

## Example 1

View complete commit history.

```bash
git log
```

Example output:

```
commit c2b1a3f9f8b...

Author: John Doe <john@example.com>

Date: Mon Jul 8 10:20:35 2025

    Add Docker support
```

---

## Example 2

Compact history.

```bash
git log --oneline
```

Output:

```
c2b1a3f Add Docker support

9fd213a Initial commit
```

---

## Example 3

Display the last three commits.

```bash
git log -3
```

---

## Example 4

Display commit graph.

```bash
git log --graph --oneline
```

Example:

```
* c2b1a3f Add Docker support

* 9fd213a Initial commit
```

---

## Example 5

Display commits from all branches.

```bash
git log --graph --decorate --all --oneline
```

Example:

```
* 73ae21d (feature/docker) Add Dockerfile

| * 2ab891c (main) Update README

|/

* a7bc812 Initial commit
```

This command is especially useful for understanding branch history and merge operations.

---

# Real-World DevOps Use Cases

## Investigating a Failed Deployment

A Kubernetes deployment suddenly starts failing.

View recent commits:

```bash
git log --oneline
```

Identify the latest infrastructure changes before troubleshooting.

---

## Finding a Terraform Change

A production infrastructure issue occurs.

View recent Terraform commits:

```bash
git log --stat
```

Determine which files were modified.

---

## Auditing Changes

Before creating a release:

```bash
git log
```

Review all commits included in the release.

---

## Reviewing Team Activity

Check contributions made during the week:

```bash
git log --since="7 days ago"
```

Useful during sprint reviews or release planning.

---

# Best Practices

- Use `git log --oneline` for everyday development.
- Use `git log --graph --decorate --all` when working with branches.
- Write meaningful commit messages to make history readable.
- Review commit history before performing reset, revert, or cherry-pick operations.

---

# Common Mistakes

## Using Only `git log`

The default output can become very long.

For daily work, many developers prefer:

```bash
git log --oneline
```

---

## Poor Commit Messages

History becomes difficult to understand when commits are named:

```
update

fix

changes

test
```

Instead:

```
Add GitHub Actions workflow

Update Kubernetes deployment

Fix Terraform variable validation
```

---

## Confusing `git log` with `git show`

`git log`

Displays multiple commits.

`git show`

Displays detailed information about a single commit.

---

# Interview Questions

### What is the purpose of `git log`?

**Answer**

It displays the commit history of a Git repository.

---

### What does `git log --oneline` do?

**Answer**

It displays a compact version of the commit history with abbreviated commit IDs and commit messages.

---

### Why is `git log --graph` useful?

**Answer**

It visually represents branch and merge history, making it easier to understand how branches relate to each other.

---

### How does Git know the order of commits?

**Answer**

Each commit stores a reference to its parent commit. `git log` follows these parent references to reconstruct the history.

---

### Which command is commonly used to visualize branch history?

**Answer**

```bash
git log --graph --decorate --all --oneline
```

---

# Summary

The `git log` command allows developers to explore the complete history of a Git repository.

It is an essential command for debugging, auditing, reviewing changes, locating commits, and understanding how a project has evolved over time.

Mastering `git log` makes advanced Git operations such as reset, revert, rebase, merge, and cherry-pick significantly easier because these operations rely on identifying the correct commit from the project's history.

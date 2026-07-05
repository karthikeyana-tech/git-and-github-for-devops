# git commit

> Create a permanent snapshot of the staged changes in a Git repository.

---

# Table of Contents

- Overview
- Purpose
- Syntax
- Common Options
- How `git commit` Works
- Examples
- Real-World DevOps Use Cases
- Best Practices
- Common Mistakes
- Interview Questions
- Summary

---

# Overview

The `git commit` command records the staged changes in the local Git repository by creating a new commit.

A commit represents a snapshot of your project at a specific point in time.

Each commit has a unique commit ID (SHA hash), allowing Git to track the complete history of the project.

A commit contains:

- Commit ID (SHA-1/SHA-256 depending on Git configuration)
- Commit message
- Author name
- Author email
- Timestamp
- Reference to the parent commit

---

# Purpose

The `git commit` command is used to:

- Save project changes permanently
- Create project history
- Track modifications
- Enable rollback to previous versions
- Record meaningful development milestones

---

# Syntax

Basic commit

```bash
git commit -m "Commit message"
```

Open default editor

```bash
git commit
```

Commit all tracked files

```bash
git commit -am "Commit message"
```

Amend previous commit

```bash
git commit --amend
```

---

# Common Options

| Option | Description |
|---------|-------------|
| `-m` | Add commit message directly from the command line |
| `-a` | Automatically stage modified tracked files before committing |
| `--amend` | Modify the most recent commit |
| `--author` | Override the commit author |

---

# How `git commit` Works

Git commits **only staged changes**.

Workflow:

```
Working Directory

↓

git add

↓

Staging Area

↓

git commit

↓

Local Repository
```

When `git commit` is executed, Git:

1. Reads the staging area.
2. Creates a snapshot of all staged files.
3. Generates a unique commit ID.
4. Stores the commit inside `.git`.
5. Moves the `HEAD` pointer to the new commit.

---

# Internal Working

Suppose the repository currently looks like this:

```
Commit A
```

You modify:

```
README.md
```

After running:

```bash
git add README.md
```

The file is staged.

Running:

```bash
git commit -m "Update README"
```

creates:

```
Commit A

↓

Commit B (HEAD)
```

Now Git permanently stores the new snapshot.

---

# Examples

## Example 1

Create a basic commit.

```bash
git add .

git commit -m "Initial commit"
```

---

## Example 2

Commit staged changes.

```bash
git commit -m "Add Docker configuration"
```

---

## Example 3

Commit all tracked modified files.

```bash
git commit -am "Update Kubernetes manifests"
```

> **Note:** The `-a` option stages only modified tracked files. It does **not** stage new (untracked) files.

---

## Example 4

Modify the latest commit.

```bash
git commit --amend
```

This is useful when:

- Commit message contains a typo
- Forgot to include one staged file
- Need to update the latest commit before pushing

---

# Real-World DevOps Use Cases

## Infrastructure as Code

After updating Terraform configuration:

```bash
git add terraform/

git commit -m "Create AWS VPC infrastructure"
```

---

## Kubernetes Deployment

After modifying deployment manifests:

```bash
git add kubernetes/

git commit -m "Update nginx deployment replicas"
```

---

## GitHub Actions

After creating a CI workflow:

```bash
git add .github/

git commit -m "Add GitHub Actions CI workflow"
```

---

## Docker

After creating a Dockerfile:

```bash
git add Dockerfile

git commit -m "Add Dockerfile for Python application"
```

---

# Writing Good Commit Messages

A commit message should clearly explain **what** changed.

Good examples:

```
Add Docker support

Configure GitHub Actions workflow

Create Kubernetes deployment manifest

Fix Nginx configuration

Update Terraform variables
```

Avoid messages like:

```
update

changes

final

test

fix
```

These provide little context.

---

# Best Practices

- Make small, logical commits.
- Write meaningful commit messages.
- Commit one logical change at a time.
- Review staged changes before committing.
- Commit frequently during development.

---

# Common Mistakes

## Forgetting to Stage Files

Running:

```bash
git commit -m "Update README"
```

without:

```bash
git add README.md
```

results in:

```
nothing added to commit
```

because Git commits only staged changes.

---

## Large Commits

Avoid combining unrelated changes in a single commit.

Bad example:

```
Updated Docker
Updated Terraform
Updated README
Fixed Kubernetes
```

Instead, create separate commits.

---

## Poor Commit Messages

Messages like:

```
update
```

make project history difficult to understand.

Prefer descriptive messages.

---

# Interview Questions

### What is a Git commit?

**Answer**

A Git commit is a snapshot of the staged changes stored permanently in the local repository.

---

### Does `git commit` save unstaged files?

**Answer**

No.

Only staged files are included in a commit.

---

### What does `git commit -am` do?

**Answer**

It stages all modified tracked files and immediately creates a commit.

It does not include new untracked files.

---

### What is the purpose of `--amend`?

**Answer**

It modifies the most recent commit by changing its message or including additional staged changes.

---

### What information does a commit contain?

**Answer**

A commit stores:

- Commit ID
- Commit message
- Author
- Email
- Timestamp
- Parent commit reference
- Snapshot of staged files

---

# Summary

The `git commit` command creates a permanent snapshot of the staged changes in a Git repository.

Commits form the project's history, making it possible to track changes, collaborate with teams, review development progress, and restore previous versions when necessary.

Writing small, meaningful commits with clear messages is a fundamental Git best practice and an essential skill for every DevOps engineer.

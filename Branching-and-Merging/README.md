# Branching and Merging

> Learn how Git branches enable parallel development, isolate features, and safely integrate changes into the main codebase.

---

# Table of Contents

- Introduction
- Learning Objectives
- What is a Branch?
- Why Branches?
- Why Branching Matters in DevOps
- Branching Strategy
- Understanding HEAD
- Branch Lifecycle
- Fast-Forward Merge
- Three-Way Merge
- Merge Conflicts
- Command Reference
- Best Practices
- Common Mistakes
- Summary

---

# Introduction

Branching is one of Git's most powerful features.

It allows developers to work on new features, bug fixes, experiments, and releases independently without affecting the stable codebase.

Instead of copying an entire project into multiple folders, Git creates lightweight branches that share history while allowing independent development.

---

# Learning Objectives

After completing this section, you will be able to:

- Explain Git branches.
- Create and switch branches.
- Merge branches safely.
- Resolve merge conflicts.
- Delete branches.
- Understand the role of `HEAD`.
- Follow a real-world Git branching workflow.

---

# What is a Branch?

A Git branch is a lightweight pointer to a sequence of commits.

Instead of creating duplicate copies of a project, Git creates a new pointer that allows independent development.

Example:

```
main

A ----- B ----- C
```

Create a feature branch:

```
main

A ----- B ----- C

               \
                D ----- E

              feature/login
```

Each branch evolves independently.

---

# Why Branches?

Without branches:

- Every developer modifies the same codebase.
- Bugs can affect production.
- Multiple features become difficult to manage.

With branches:

- Features remain isolated.
- Teams work in parallel.
- Code reviews become easier.
- Production stays stable.

---

# Why Branching Matters in DevOps

Branching is fundamental to DevOps workflows.

Typical examples include:

- Feature development
- Infrastructure updates
- Hotfixes
- Release preparation
- CI/CD testing

Example:

```
Developer

↓

Feature Branch

↓

Pull Request

↓

Code Review

↓

Merge into main

↓

CI/CD Pipeline

↓

Production
```

---

# Branching Strategy

A common workflow is:

```
main

↓

feature/login

↓

feature/payment

↓

feature/docker

↓

Merge

↓

main
```

Every feature is developed independently before being merged into the main branch.

---

# Understanding HEAD

`HEAD` represents your current location in the repository.

Example:

```
main

A ---- B ---- C
              ↑
            HEAD
```

Switch branches:

```
feature/login

A ---- B ---- C ---- D
                   ↑
                 HEAD
```

Git moves `HEAD` to the active branch.

---

# Branch Lifecycle

Typical lifecycle:

```
Create Branch

↓

Develop

↓

Commit

↓

Merge

↓

Delete Branch
```

This is the standard workflow followed by most software and DevOps teams.

---

# Fast-Forward Merge

Occurs when the target branch has not changed since the feature branch was created.

```
A ---- B ---- C

               \
                D
```

Merge:

```
A ---- B ---- C ---- D
```

Git simply moves the branch pointer forward.

---

# Three-Way Merge

Occurs when both branches have progressed independently.

```
          D

         /

A ---- B ---- C

         \

          E
```

Git creates a new merge commit.

---

# Merge Conflicts

A merge conflict occurs when Git cannot automatically determine which changes should be kept.

Typical causes:

- Same file
- Same lines
- Different modifications

Git pauses the merge and asks the developer to resolve the conflict manually.

---

# Command Reference

Detailed documentation is available for:

| Command | Documentation |
|----------|---------------|
| `git branch` | commands/git-branch.md |
| `git switch` | commands/git-switch.md |
| `git checkout` | commands/git-checkout.md |
| `git merge` | commands/git-merge.md |
| `git branch -d` | commands/git-branch-delete.md |
| Merge Conflict Resolution | commands/git-merge-conflict.md |

---

# Best Practices

- Create one branch per feature.
- Keep branches short-lived.
- Merge frequently.
- Delete merged branches.
- Never develop directly on `main`.
- Use descriptive branch names.

Examples:

```
feature/docker

feature/github-actions

bugfix/nginx

hotfix/security

release/v1.2.0
```

---

# Common Mistakes

- Working directly on `main`.
- Keeping feature branches alive for months.
- Mixing unrelated changes in one branch.
- Ignoring merge conflicts.
- Forgetting to delete merged branches.

---

# Summary

Branching allows multiple developers to work independently while keeping the main branch stable.

Combined with merging, it forms the foundation of collaborative Git workflows used in modern DevOps environments.

Understanding branching is essential before learning GitHub Pull Requests, Git Flow, GitHub Flow, and CI/CD pipelines.

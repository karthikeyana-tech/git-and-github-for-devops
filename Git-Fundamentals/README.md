# Git Fundamentals

> Learn the core concepts of Git and build a strong foundation for version control before exploring advanced Git and GitHub workflows.

---

# Table of Contents

- Introduction
- Learning Objectives
- Prerequisites
- What is Version Control?
- Types of Version Control Systems
- What is Git?
- Why Git?
- Why Git for DevOps?
- Git Architecture
- Git Workflow
- Command Reference
- Best Practices
- Common Mistakes
- Summary
- Next Steps

---

# Introduction

Git is a Distributed Version Control System (DVCS) that helps developers and DevOps engineers track changes, collaborate efficiently, maintain project history, and recover previous versions whenever needed.

It is the industry standard for version control and forms the foundation of modern DevOps workflows.

---

# Learning Objectives

After completing this section, you will be able to:

- Explain Version Control Systems.
- Understand how Git stores project history.
- Explain Git Architecture.
- Understand the Git workflow.
- Create your first Git repository.
- Make commits confidently.

---

# Prerequisites

- Basic Linux commands
- Basic terminal knowledge

---

# What is Version Control?

Version Control is a system that records changes made to files over time, allowing developers to:

- Track modifications
- Restore previous versions
- Compare changes
- Collaborate with teams
- Maintain project history

Without version control:

```
project-final/
project-final-v2/
project-final-final/
```

With Git:

```
project/
└── .git/
```

Git stores every version efficiently inside the `.git` directory.

---

# Types of Version Control Systems

## Local Version Control System

Stores history on one computer.

Examples

- RCS

Advantages

- Simple

Disadvantages

- No collaboration
- No backup

---

## Centralized Version Control System

Examples

- SVN
- Perforce

Single central server.

Advantages

- Central administration

Disadvantages

- Single point of failure.

---

## Distributed Version Control System

Examples

- Git
- Mercurial

Every developer has a complete copy of the repository.

Advantages

- Offline work
- Fast operations
- Better collaboration
- Full history available locally

---

# What is Git?

Git is an open-source Distributed Version Control System created by Linus Torvalds in 2005.

Unlike traditional systems, Git stores project snapshots instead of only file differences, making operations fast and reliable.

---

# Why Git?

Git helps developers:

- Track code history
- Restore previous versions
- Work safely with teams
- Create independent feature branches
- Merge work efficiently

---

# Why Git for DevOps?

Almost every DevOps tool integrates with Git.

Examples:

- Docker
- Kubernetes
- Terraform
- Ansible
- GitHub Actions
- Jenkins
- ArgoCD

Git becomes the single source of truth for infrastructure and application code.

---

# Git Architecture

Git manages files using three areas:

Working Directory

↓

Staging Area

↓

Local Repository

Each Git command moves data between these areas.

Detailed explanations are available in the individual command documentation.

---

# Git Workflow

```
Create File

↓

git status

↓

git add

↓

git commit

↓

git push
```

This workflow is the foundation of Git.

---

# Command Reference

The following commands are documented separately.

| Command | Documentation |
|----------|---------------|
| git --version | commands/git-version.md |
| git config | commands/git-config.md |
| git init | commands/git-init.md |
| git status | commands/git-status.md |
| git add | commands/git-add.md |
| git commit | commands/git-commit.md |
| git log | commands/git-log.md |

---

# Best Practices

- Commit small logical changes.
- Write meaningful commit messages.
- Review changes before committing.
- Keep repositories focused on one project.
- Use Git regularly.

---

# Common Mistakes

- Forgetting Git configuration.
- Using vague commit messages.
- Skipping `git status`.
- Initializing nested Git repositories.

---

# Summary

Git is the foundation of modern software development and DevOps.

Understanding Git Fundamentals makes advanced topics like branching, merging, rebasing, pull requests, CI/CD, and GitHub much easier.

---

# Next Steps

Continue with:

**Branching and Merging**

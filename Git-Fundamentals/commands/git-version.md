# git --version

> Display the installed Git version.

---

# Table of Contents

- Overview
- Purpose
- Syntax
- Parameters
- Internal Working
- Examples
- Real-World DevOps Use Case
- Best Practices
- Common Mistakes
- Interview Questions
- Related Commands
- Summary

---

# Overview

The `git --version` command displays the currently installed Git version on your system.

It is usually the first command executed after installing Git to verify that the installation completed successfully.

---

# Purpose

- Verify Git installation.
- Check the installed Git version.
- Confirm compatibility with project requirements.
- Troubleshoot Git-related issues.

---

# Syntax

```bash
git --version
```

---

# Parameters

This command does not require any parameters.

---

# Internal Working

When executed, Git reads its installed version information and prints it to the terminal.

Unlike most Git commands, it does not interact with:

- Repository
- Working Directory
- Staging Area
- Commit History

It simply reports the installed Git version.

---

# Example

```bash
git --version
```

Output

```text
git version 2.43.0
```

The version displayed may differ depending on your installation.

---

# Real-World DevOps Use Case

A DevOps engineer logs into a newly provisioned Linux server before configuring a CI/CD pipeline.

The first step is verifying that Git is available:

```bash
git --version
```

If Git is missing or outdated, it can be installed or upgraded before cloning repositories or running automation.

---

# Best Practices

- Verify Git installation after installing it.
- Ensure your Git version meets project requirements.
- Keep Git updated to receive security patches and new features.

---

# Common Mistakes

## Git is not installed

```text
git: command not found
```

Install Git using your operating system's package manager.

---

## Using an outdated version

Older versions may not support newer Git features or options.

---

# Interview Questions

### What is the purpose of `git --version`?

**Answer:**

It displays the installed Git version and verifies that Git is available on the system.

---

### Does `git --version` require a Git repository?

**Answer:**

No. It can be executed from any directory.

---

# Related Commands

- `git config`
- `git help`
- `git --help`

---

# Summary

The `git --version` command is a simple diagnostic command used to verify that Git is installed and to identify the installed version. It is commonly used after installation and during environment verification.

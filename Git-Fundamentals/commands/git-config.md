# git config

> Configure Git settings such as username, email, default branch, editor, and other repository-specific or global preferences.

---

# Table of Contents

- Overview
- Purpose
- Syntax
- Configuration Levels
- Common Configuration Options
- Internal Working
- Examples
- Real-World DevOps Use Cases
- Best Practices
- Common Mistakes
- Interview Questions
- Related Commands
- Summary

---

# Overview

The `git config` command is used to view, add, update, or remove Git configuration settings.

Git stores configuration values at different levels, allowing you to define settings for:

- The entire system
- A specific user
- A specific repository

These settings control Git's behavior, including commit author information, default editor, merge tools, line ending handling, and more.

---

# Purpose

The `git config` command is commonly used to:

- Set your username
- Set your email address
- Configure the default branch name
- Choose a default text editor
- View existing Git configuration
- Customize Git behavior

---

# Syntax

```bash
git config [options] <key> <value>
```

Common examples:

```bash
git config --global user.name "John Doe"

git config --global user.email "john@example.com"

git config --list
```

---

# Configuration Levels

Git supports three configuration levels.

## 1. System Configuration

Applies to every user on the machine.

```bash
git config --system
```

Configuration file:

```text
/etc/gitconfig
```

Typically modified by system administrators.

---

## 2. Global Configuration

Applies only to the current user.

```bash
git config --global
```

Configuration file:

```text
~/.gitconfig
```

or

```text
~/.config/git/config
```

This is the most commonly used configuration level.

---

## 3. Local Configuration

Applies only to the current repository.

```bash
git config
```

Configuration file:

```text
.git/config
```

Local settings override global settings.

---

# Configuration Priority

When Git reads configuration values, it uses the following priority:

```text
Local Repository

↓

Global

↓

System
```

The nearest configuration always takes precedence.

---

# Common Configuration Options

## Configure Username

```bash
git config --global user.name "John Doe"
```

Purpose:

Defines the author name for future commits.

Verify:

```bash
git config --global user.name
```

---

## Configure Email

```bash
git config --global user.email "john@example.com"
```

Purpose:

Associates commits with an email address.

Verify:

```bash
git config --global user.email
```

---

## View All Configuration

```bash
git config --list
```

Example output:

```text
user.name=John Doe
user.email=john@example.com
core.editor=nano
init.defaultBranch=main
```

---

## Set Default Branch

```bash
git config --global init.defaultBranch main
```

Purpose:

Makes newly initialized repositories use `main` instead of `master`.

---

## Configure Default Editor

Nano:

```bash
git config --global core.editor nano
```

VS Code:

```bash
git config --global core.editor "code --wait"
```

Purpose:

Git uses this editor when writing commit messages or resolving merges.

---

# Internal Working

Git stores configuration as key-value pairs.

Example:

```ini
[user]
    name = John Doe
    email = john@example.com

[core]
    editor = nano

[init]
    defaultBranch = main
```

These values are stored in configuration files depending on the chosen level.

Git reads them whenever a command requires configuration information.

---

# Examples

## Example 1

Configure Git for the first time.

```bash
git config --global user.name "John Doe"

git config --global user.email "john@example.com"
```

---

## Example 2

Display all configured values.

```bash
git config --list
```

---

## Example 3

View only the configured username.

```bash
git config --global user.name
```

---

## Example 4

Configure a repository-specific username.

```bash
git config user.name "Project Bot"
```

This affects only the current repository.

---

# Real-World DevOps Use Cases

## Multiple GitHub Accounts

A DevOps engineer uses:

- Personal GitHub account
- Company GitHub Enterprise account

Global configuration:

```bash
git config --global user.name "John Doe"
```

Company repository:

```bash
git config user.name "John Doe (Company)"
```

The local configuration overrides the global configuration only for that repository.

---

## CI/CD Pipelines

Automation tools such as Jenkins or GitHub Actions may create commits.

Before committing, the pipeline configures Git:

```bash
git config user.name "GitHub Actions"

git config user.email "actions@github.com"
```

This identifies the automation as the commit author.

---

# Best Practices

- Configure your username and email before creating commits.
- Use global configuration for personal settings.
- Use local configuration for project-specific requirements.
- Set the default branch to `main`.
- Verify configuration using `git config --list`.

---

# Common Mistakes

## Forgetting to Configure Git

Attempting to commit before setting your identity results in an error similar to:

```text
Author identity unknown
```

Git cannot create commits until your username and email are configured.

---

## Using the Wrong Email Address

Using a different email from your GitHub account may prevent commits from appearing on your GitHub contribution graph.

---

## Confusing Global and Local Configuration

Running:

```bash
git config user.name "John Doe"
```

inside a repository changes only that repository.

Running:

```bash
git config --global user.name "John Doe"
```

changes the setting for all repositories owned by the current user.

---

# Interview Questions

### What is the purpose of `git config`?

**Answer:**

It is used to configure and manage Git settings at the system, global, or local repository level.

---

### What are the three Git configuration levels?

**Answer:**

- System
- Global
- Local

---

### Which configuration has the highest priority?

**Answer:**

Local repository configuration.

---

### Where is the global Git configuration stored?

**Answer:**

Typically in:

```text
~/.gitconfig
```

---

### How do you view all Git configuration values?

```bash
git config --list
```

---

# Related Commands

- `git --version`
- `git init`
- `git status`
- `git commit`

---

# Summary

The `git config` command allows you to customize Git's behavior by storing configuration values at the system, global, or local level.

Understanding configuration levels is essential for working across multiple repositories, collaborating with teams, and building reliable DevOps automation.

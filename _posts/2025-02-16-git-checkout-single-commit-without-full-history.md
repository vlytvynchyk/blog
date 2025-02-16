---
date: 2025-02-16
tag: git
title: "[Git] Checkout a single commit without full history"
description: "Learn how to efficiently fetch and checkout a specific commit from a Git repository without downloading the entire history. This technique is ideal for code reviews and optimizing CI jobs."
---

In my day-to-day work, I often review code and typically don't need the full repository history—just the latest commit. Since a repository's history can be massive, I prefer to check out only the specific commit I need. This approach is also useful when configuring a CI job that needs to pull a repository.

## Create and enter an empty directory

```bash
mkdir my-repo && cd my-repo
```

## Initialize a new Git repository

```bash
git init
```

## Add the remote repository

```bash
git remote add origin <repository_url>
```

## Fetch only the specific commit (with depth 1)

```bash
git fetch --depth 1 origin <commit_sha>
```

## Check out the fetched commit

```bash
git checkout FETCH_HEAD
```


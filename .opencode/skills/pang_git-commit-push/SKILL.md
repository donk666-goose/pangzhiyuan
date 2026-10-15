---
name: pang_git-commit-push
description: Use when committing changes and pushing the current project to the Gitee repository at https://gitee.com/pangzhiyuan-200481/pangzhiyuan2026.git. Handles git add, commit, and push with proper verification steps.
---

# Git Commit and Push to Gitee

## Remote Repository

- URL: `https://gitee.com/pangzhiyuan-200481/pangzhiyuan2026.git`
- Name: `gitee`

## Workflow

### 1. Inspect Current State

Run these commands to understand the repository status before making any changes:

```bash
git status
git diff
git log --oneline -10
```

### 2. Stage Files

- Stage only intended files — never commit secrets or unrelated changes
- Use `git add <specific files>` rather than `git add .` unless ALL changes are intentional
- If the remote `gitee` does not exist yet, add it:
  ```bash
  git remote add gitee https://gitee.com/pangzhiyuan-200481/pangzhiyuan2026.git
  ```
  If it already exists, verify with:
  ```bash
  git remote -v
  ```

### 3. Commit

- Write a concise commit message that matches the repo style (short, imperative, no body unless needed)
- Stage files and commit:
  ```bash
  git add <files>
  git commit -m "descriptive message"
  ```

### 4. Push

- Push to the `gitee` remote:
  ```bash
  git push gitee <branch-name>
  ```
- If the branch is new to the remote, use `-u` to set upstream:
  ```bash
  git push -u gitee <branch-name>
  ```
- If push is rejected (non-fast-forward), pull first then push:
  ```bash
  git pull --rebase gitee <branch-name>
  git push gitee <branch-name>
  ```

### 5. Verify

- Confirm the push succeeded by checking the output of `git push`
- If a hook or permission error occurs, report the exact error message to the user

## Safety Rules

- NEVER use `git push --force` unless the user explicitly requests it
- NEVER commit files containing secrets, keys, or credentials
- NEVER amend a commit that has already been pushed without explicit user request
- Always show the user what will be committed before running `git commit`

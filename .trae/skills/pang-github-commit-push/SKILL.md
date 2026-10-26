---
name: pang-github-commit-push
description: Commit changes and push the current project to the GitHub repository donk666-goose/pangzhiyuan. Use when the user asks to commit, push, upload, or sync code to GitHub. Do not use for the Gitee repository pangzhiyuan2026, force push, or committing secrets.
---

# Git Commit and Push to GitHub

## Remote Repository

- URL: `git@github.com:donk666-goose/pangzhiyuan.git` (SSH，公钥已配置)
- HTTPS alternative: `https://github.com/donk666-goose/pangzhiyuan.git`
- Remote name: `github`

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
- Verify the remote exists with `git remote -v`; if missing, add it:

```bash
git remote add github git@github.com:donk666-goose/pangzhiyuan.git
```

### 3. Commit

- Write a concise commit message that matches the repo style (short, imperative, no body unless needed)
- Stage files and commit:

```bash
git add <files>
git commit -m "descriptive message"
```

### 4. Push

- Push to the `github` remote:

```bash
git push github <branch-name>
```

- If the branch is new to the remote, use `-u` to set upstream:

```bash
git push -u github <branch-name>
```

- If push is rejected (non-fast-forward), pull first then push:

```bash
git pull --rebase github <branch-name>
git push github <branch-name>
```

### 5. Verify

- Confirm the push succeeded by checking the output of `git push`
- If SSH authentication fails, run `ssh -T git@github.com` to check the key, then report the exact error to the user
- If a hook or permission error occurs, report the exact error message to the user

## Safety Rules

- NEVER use `git push --force` unless the user explicitly requests it
- NEVER commit files containing secrets, keys, or credentials
- NEVER amend a commit that has already been pushed without explicit user request
- Always show the user what will be committed before running `git commit`

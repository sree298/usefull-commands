## 🧠 Git Commands

---

### 🔧 Git Config

| Command | Description |
|--------|-------------|
| `git config` | Set username and email details |
| `git config --list` | Show all git config details |
| `git config --global user.name "Your Name"` | Configure global username |
| `git config --global user.email "email-id"` | Configure global email |
| `git config --global --edit` | Edit config file |

---

### 📂 Repository Setup

| Command | Description |
|--------|-------------|
| `git init` | Create empty local repository |
| `git add <file-name>` | Move file to staging area |
| `git commit -m "message"` | Commit staged changes |
| `git status` | Check modified files |
| `git log` | Check commit history |

# 🧰 Git Remote Commands

| Command | Description |
|--------|-------------|
| `git remote -v` | Show remote URLs |
| `git remote add <name> <url>` | Add remote |
| `git remote rename <old> <new>` | Rename remote |
| `git remote set-url <name> <url>` | Change remote URL |
| `git push origin master` | Push to master branch |
| `git clone <repo-url>` | Clone remote repository |

## 📜 Git Log Commands

| Command | Description |
|--------------------------------|--------------------------|
| `git log -n 5` | Show last 5 commits |
| `git log --author=<name>` | Filter commits by author |
| `git log <file-path>` | Show commit history for specific file |
| `git reflog` | Show reference log changes (all HEAD changes) |

## 🔄 Git Sync Commands (Fetch / Pull / Push)

| Command     | Description                     |
|------------|---------------------------------|
| `git fetch` | Download changes without merging |
| `git pull`  | Fetch + merge changes to current branch |
| `git push`  | Upload local commits to remote repository |

## 🏷️ Git Tag Commands

| Command | Description |
|--------|-------------|
| `git tag` | Show all tags |
| `git tag -a <tag> -m "msg"` | Create an annotated tag |
| `git push origin <tag>` | Push tag to remote |
| `git checkout <tag>` | Checkout a specific tag |
| `git tag -d <tag>` | Delete a local tag |

## 🌿 Git Branch Commands

| Command | Description |
|---------|-------------|
| `git branch` | List all branches |
| `git branch <branch>` | Create a new branch |
| `git checkout <branch>` | Switch to branch |
| `git branch -d <branch>` | Delete local branch |
| `git push origin --delete <branch>` | Delete remote branch |

## 🔁 Git Merge & Rebase Commands

| Command | Description |
|--------|-------------|
| `git merge <branch>` | Merge a branch into the current branch |
| `git rebase <branch>` | Reapply commits from another branch on top of current |
| `git merge` vs `git rebase` | **Merge:** preserves full history & creates merge commit<br>**Rebase:** creates clean linear history |

## ♻ Git Undo / Reset / Revert Commands

| Command | Description |
|--------|-------------|
| `git reset --soft <commit>` | Undo commit but keep changes staged |
| `git reset --mixed <commit>` | Undo commit & unstage changes (default reset) |
| `git reset --hard <commit>` | Undo commit & discard working directory changes |
| `git revert <commit>` | Create a new commit to undo changes safely |

## 🧺 Git Stash Commands

| Command | Description |
|--------|-------------|
| `git stash` | Store uncommitted changes temporarily |
| `git stash list` | Show saved stash items |
| `git stash apply` | Apply the most recent stash |
| `git stash pop` | Apply & remove last stash |
| `git stash drop stash@{n}` | Delete a specific stash |

## 🧠 Advanced Git Commands

| Command | Description |
|--------|-------------|
| `git cherry-pick <commit>` | Apply a commit from another branch to the current branch |
| `git commit --amend -m "msg"` | Modify / rewrite the most recent commit message |
| `git squash (rebase -i)` | Combine multiple commits into a single commit |



## 🚀 Git Push Example (Complete Workflow)

```bash
mkdir demo-repo
cd demo-repo
git init
git add test.txt
git commit -m "initial commit"
git remote add origin <github-url>
git push origin master


---

### If you want a separator before it:
```markdown
---

## 🚀 Git Push Example (Complete Workflow)

```bash
mkdir demo-repo
cd demo-repo
git init
git add test.txt
git commit -m "initial commit"
git remote add origin <github-url>
git push origin master








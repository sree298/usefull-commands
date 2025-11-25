# Git Interview Commands & Explanation

---

## Basic Commands

| Command | Description | Example |
|---------|-------------|----------|
| **git config** | Set user-name and email-id, that will attach to commit-id and tag commands. | `git config --list` |
| | | `git config --global user.name "Your Name"` |
| | | `git config --global user.email "email-id"` |
| | | `git config --global --edit` |

---

## Initialize Repository

| Command | Description | Example |
|---------|-------------|----------|
| **git init** | To create an empty local repo. | `mkdir my-repo` <br> `cd my-repo` <br> `git init` |

---

## Add & Commit

| Command | Description | Example |
|---------|-------------|----------|
| **git add** | Move the changes from working area to staging area. | `git add <file-name>` |
| **git commit** | Move changes from staging area to local repo. | `git commit -m "commit-message"` |

---

## Remote Repo

| Command | Description | Example |
|---------|-------------|----------|
| **git remote** | Add remote registry URL (GitHub). | `git remote -v` |
| | | `git remote add <name> <url>` |
| | | `git remote rename <old_name> <new_name>` |
| | | `git remote set-url <name> <new_url>` |

---

## Repository Status & History

| Command | Description | Example |
|---------|-------------|----------|
| **git status** | Check the status of modified files. | `git status` |
| **git log** | Check the commit history. | `git log -n 5` |
| | | `git log <file_path>` |
| | | `git log --author=<author_name>` |
| | | `git log --since=<date> --until=<date>` |

---

## Push, Clone, Fork

| Command | Description | Example |
|---------|-------------|----------|
| **git push** | Upload local repo changes to remote repo. | `git push <remote_name> <branch_name>` |
| | | `git push origin master` |
| **git clone** | Used to create a copy of a remote Git repository on local machine. This allows you to start working with the repository and make changes to it locally. | `git clone <repository_url>` |
| | | `git clone https://github.com/exampleuser/example-repo.git` |
| **git fork** | Copy remote repo from one account to another. | Done from GitHub UI |

---

## Recovery & History

| Command | Description | Example |
|---------|-------------|----------|
| **git reflog** | Store all git commit historical changes & information. | `git reflog` |
| | | `git reflog show <branch_name>` |

---

## Remove, Fetch, Pull

| Command | Description | Example |
|---------|-------------|----------|
| **git rm** | Remove files from working directory. | `git rm <file>` |
| **git fetch** | Downloads changes from a remote repo to the local repo **without merging** into the current local branch.<br><br>• Updates the local copy of remote branch(es) but **does not modify the working directory or local branches**.<br>• After fetching, we can inspect the changes using commands like `git log` or `git diff`, and then decide how to merge the changes into local branches. | `git fetch` <br> `git fetch origin master` |
| **git pull** | Fetch + Merge from remote repo to current branch. | `git pull` <br> `git pull origin master` |

---

## Tagging

| Command | Description | Example |
|---------|-------------|----------|
| **git tag** | Application milestones and release versions. | `git tag` |
| | | `git tag -a <tag_name> -m "tag message"` |
| | | `git tag <tag_name> <commit_sha>` |
| | | `git push origin <tag_name>` |
| | | `git tag -d <tag_name>` |
| | | `git checkout <tag_name>` |

---

## Compare & Show Differences

| Command | Description | Example |
|---------|-------------|----------|
| **git diff** | Check code difference between commits, branches, files. | `git diff <commit1> <commit2>` |
| | | `git diff` |
| | | `git diff <file_name>` |
| | | `git diff <branch1> <branch2>` |
| **git show** | Show details of a single commit. | `git show <commit_id>` |
| | | `git show <commit_id>:<file_path>` |

---


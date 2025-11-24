#### GIT-INIT FLOW
#### DEVELOPER-1
# Git Merge Practice – Local to Remote Push Steps

## 1. Create project directory and initialize local repository

```bash
mkdir merge-practices
cd merge-practices
git init   # Created local repo
git config --global user.name "developer-1"
git config --global user.email "developer-1@gmail.com"
echo "Master line-1" >> index.html
git status
git add index.html
git status
git commit -m "M1"
git branch -M main
git status
git log --decorate --oneline --graph
-------------------------------------------
echo "Master line-2" >> index.html
git status
git commit -am "M2"
git status
git log --decorate --oneline --graph
------------------------------
```
#### IN GITHUB CREATE THE REPO, IN "merge-practices" NAME.
#### adding remote server/GITHUB url.
```bash
git remote add origin git@github.com:sree298/merge-practices.git
```
#### pushed the changes to remote server/GITHUB.
```bash
git push origin main
```
# GIT COMMANDS

| Command | Description |
|---------|-------------|
| `git config` | Set name and email-id that will be attached to your commits and tags |
| `git init` | Create an empty local repository |
| `git clone` | Download the code from a remote repository |
| `git fork` | Copy a remote repository from one GitHub account to another |
| `git pull` | Download changes from remote repository to working area |
| `git fetch` | Download changes from remote repository to local repository |
| `git push` | Upload changes from local repository to remote repository |
| `git add` | Move changes from working area to staging area |
| `git commit` | Move changes from staging area to local repository |
| `git tag` | Indicates application milestones (versioning) |
| `git status` | Check the status of modified and staged files |
| `git log` | View commit history |
| `git diff` | Check difference between working/staged/committed changes |
| `git show` | Display details of a specific commit |
| `git reflog` | Stores complete Git historical reference information |
| `git branch` | Create/manage branches (parallel development) |
| `git merge` | Merge feature branch code into main/master branch |
| `git rebase` | Rewrite commit history into linear format |
| `git reset` | Undo changes in the local repository |
| `git revert` | Undo changes in remote repository by creating new commit |
| `git rm` | Remove a file from working directory and staging |
| `git checkout` | Switch branches or restore files |
| `git remote` | Add remote registry URL (GitHub) |
| `git stash` | Temporarily store uncommitted changes in a hidden area |
| `git squash` | Combine multiple commits into a single commit |
| `git cherry-pick` | Apply a specific commit from another branch |
| `git amend` | Modify the most recent commit |
### GIT-MERGE - - > Copy code from feature branch to mainbranch
#### DEVELOPER-2
```bash
git config --global --list
git clone -b main git@github.com:sree298/merge-practices.git
```
#### IN GIT CLONE:
1. Not required to do git init. it will create local repo by default.
2. Not required to add origin/GITHUB url. it will came by default.
```bash
cd merge-practices
```
#### Verify the current branch name
```bash
git branch
```
#### Created feature new branch AND switched to new feature branch
```bash
git checkout -b feature
```
(OR)
#### Switched to existing feature branch
```bash
git checkout feature
git status
git log --decorate --oneline --graph
------------------------------
echo "Feature line-1" >> nginx.conf
git status
git commit -am "F1"  #--> This command will not work for newly created files.
git add nginx.conf
git status
git commit -m "F1"
git status
git log --decorate --oneline --graph
------------------------------
echo "Feature line-2" >> nginx.conf
git status
git commit -am "F2"
git status
git log --decorate --oneline --graph
```
------------------------------
#### if you are not passing origin, branch name, it will consider default values.
```bash
git push origin feature
```
### Types of merge
1. Merge.
2. Fast Forward Merge.
3. Squash and Merge.
<img width="750" height="542" alt="Centralized Version Control System" src="../../images/workstation.png" />

#### Merge - process
<img width="750" height="542" alt="Centralized Version Control System" src="../../images/merge.png" />

<img width="750" height="542" alt="Centralized Version Control System" src="../../images/merge1.png" />

<img width="750" height="542" alt="Centralized Version Control System" src="../../images/merge2.png" />

### Save and Exit Commands in Editor (nano)

Press → **Ctrl + X**  
Press → **Y**  
Press → **Enter**

<img width="750" height="542" alt="Centralized Version Control System" src="../../images/merge3.png" />

#### Fast Forward Merge

<img width="750" height="542" alt="Centralized Version Control System" src="../../images/fastforward.png" />

#### Squash and Merge 

<img width="750" height="542" alt="Centralized Version Control System" src="../../images/Squash.png" />

<img width="750" height="542" alt="Centralized Version Control System" src="../../images/Squash2.png" />

### Delete Git Branch

#### Delete branch in local repository
```bash
git branch -D feature    # Delete branch on local repo
```
#### Delete branch in remote repository
```bash
git push origin --delete feature    # Delete branch on remote repo
```
### GIT MERGE Vs REBASE

<img width="750" height="542" alt="Centralized Version Control System" src="../../images/worstation1.png" />
<img width="750" height="542" alt="Centralized Version Control System" src="../../images/mergerrebase.png" />
<img width="750" height="542" alt="Centralized Version Control System" src="../../images/rebaseedit.png" />
<img width="750" height="542" alt="Centralized Version Control System" src="../../images/rebaseedit1.png" />
<img width="750" height="542" alt="Centralized Version Control System" src="../../images/rebaseedit2.png" />

### Save and Exit Commands in Editor (nano)

Press → **Ctrl + X**  
Press → **Y**  
Press → **Enter**

<img width="750" height="542" alt="Centralized Version Control System" src="../../images/rebaseedit3.png" />

#### GIT UNDO (STASH, CHECKOUT, RESET, REVERT)

<img width="750" height="542" alt="Centralized Version Control System" src="../../images/workstations.png" />

### GIT REST - -> Remove Last commit changes from local repo
#### Types of REST
1. soft
2. mixed
3. hard
#### Before reset
<img width="750" height="542" alt="Centralized Version Control System" src="../../images/beforerest.png" />

#### After soft reset (Only changes removed on local repo)

<img width="750" height="542" alt="Centralized Version Control System" src="../../images/aferrest.png" />


#### After mixed reset (changes removed on local repo + staging area)

<img width="750" height="542" alt="Centralized Version Control System" src="../../images/aftermixed.png" />


#### After hard reset (changes removed on local repo + staging area + working area)

<img width="750" height="542" alt="Centralized Version Control System" src="../../images/afterhard.png" />

## GIT REVERT

**`git revert` → Remove the last commit changes from remote repository**

### Key points:
1. It is a **safe way** to remove commit changes from a remote repo.
2. Because the **removed commit ID still exists in Git logs**, and a **new commit** will be added for justification of removal.
   - (History is preserved — nothing is lost)

---
## GIT REVERT on Remote Repo (Important Note)

- `git revert` does **NOT remove** the old commit from history.
- Instead, it creates a **new commit**: `Revert "<message>"`.
- The old commit (ex: `MC1`) will still show in **GitHub commit history**.
- But the latest commit (`Revert "MC1"`) **undoes the changes** from `MC1`.

### Example sequence

MC1          → Adds nginx.conf  
Revert "MC1" → Deletes nginx.conf (undoes MC1)

Result:  
- History shows: `Revert "MC1"`, `MC1`, `F2`, `F1`, `M2`, `M1`  
- But final code is **as if MC1 never happened**.
If you **want MC1 to totally disappear from history**, that’s when we use:
```bash
- git reset --hard <commit-id>
- git push -f origin main
```
…but that is **dangerous in team projects**.

### Before REVERT

<img width="750" height="542" alt="Centralized Version Control System" src="../../images/beforerevert1.png" />
<img width="750" height="542" alt="Centralized Version Control System" src="../../images/beforerevert2.png" />

## GIT REVERT Steps

```bash
git log --decorate --oneline --graph    # Check commit history
git revert 400c46d                      # Revert the selected commit ID
git status
vi index.html                           # Resolve conflicts (if any)
git add index.html                      # Add resolved file
git revert --continue                   # Continue revert process
git log --decorate --oneline --graph    # Verify revert commit history
git push origin master                  # Push reverted changes to remote
```

<img width="750" height="542" alt="Centralized Version Control System" src="../../images/gitrevert.png" />
<img width="750" height="542" alt="Centralized Version Control System" src="../../images/gitrevert1.png" />
<img width="750" height="542" alt="Centralized Version Control System" src="../../images/gitrevert2.png" />
<img width="750" height="542" alt="Centralized Version Control System" src="../../images/gitrevert3.png" />
<img width="750" height="542" alt="Centralized Version Control System" src="../../images/gitrevert4.png" />

### After REVERT
<img width="750" height="542" alt="Centralized Version Control System" src="../../images/afterrevert.png" />
<img width="750" height="542" alt="Centralized Version Control System" src="../../images/afterrevert1.png" />

### Git pull vs fetch

<img width="750" height="542" alt="Centralized Version Control System" src="../../images/pullfetch.png" />

### Git clone vs fork
#### Fork operation will do on GITHUB UI

<img width="750" height="542" alt="Centralized Version Control System" src="../../images/clonefork.png" />

<img width="750" height="542" alt="Centralized Version Control System" src="../../images/forkvsclone.png" />



## GIT DIFF Commands

```bash
git diff commit-1 commit-2         # Shows the differences between two commit IDs
git diff <file-name>               # Shows the file-level differences
git diff master origin/master      # Shows the differences between local and remote branches
```
## GIT LOG Commands

```bash
git log --decorate --oneline --graph   # Shows all commit logs in graph view
git log -n 2                           # Shows the last 2 commit logs
git log -p <file-name>                 # Shows commit history and patch details for a specific file
```
## GIT TAG Commands

```bash
git tag                                  # Shows the available tag list
git tag <tag-name> <commit-id> -a -m "message"   # Create an annotated tag
Example:
git tag V1.0 49b25b4 -a -m "May-2022 release"
git show-ref --tags                      # Shows tag references and commit mapping
git show <tag-name>                      # Shows the tag commit history
git push origin --tags                   # Push all tags to remote server
git push origin V1.0                     # Push specific tag to remote server
git pull origin --tags                   # Pull all tags from remote server
git checkout tags/<tag_name> -b <branch_name>   # Checkout from a tag to a new branch
git tag -d <tag-name>                    # Delete tag locally
```

## GIT AMEND Practice Example

```bash
mkdir amend-practice
cd amend-practice
git init
echo "Master line-1" >> index.html
git status
git add index.html
git status
git commit -m "M1"
git status
git log --decorate --oneline --graph
echo "Master line-2" >> index.html
git status
git add index.html
git status
git commit --amend -m "M1"
OR
git commit --amend -m "M1-A"     # Modify commit message
git status
git log --decorate --oneline --graph
```
## GIT SQUASH

### Using Merge (Squash commits of a feature branch into a single commit)

```bash
git merge --squash feature
git rebase -i HEAD~3
```
<img width="750" height="542" alt="Centralized Version Control System" src="../../images/sqash1.png" />
<img width="750" height="542" alt="Centralized Version Control System" src="../../images/sqash2.png" />
<img width="750" height="542" alt="Centralized Version Control System" src="../../images/sqash3.png" />

## GIT STASH Commands

```bash
git stash          # Move uncommitted changes to hidden stash area
git stash pop      # Restore stashed files and remove from stash list
git stash list     # Check all stash entries
git stash drop     # Remove a specific stash entry
```
<img width="750" height="542" alt="Centralized Version Control System" src="../../images/STASH.png" />

## GIT CHERRY-PICK

```bash
git cherry-pick <commit-id>     # Apply a specific commit from another branch to the current branch
```












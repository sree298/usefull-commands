#### setup the name and email that will be attached your commit and tags
```bash
git config --global user.name "sree"
git config --global user.email "sree@gmail.com"
git config --global --list
```
#### Set up local repo
#### Option-1
#### Create a new directory
```bash
$ mkdir git-demo
```
#### Navigate to git-demo directory
```bash
$ cd git-demo
```
#### Create the new local-repo
```bash
$ git init
```
---------------------
#### Option-2
#### Clone the repo from GITHUB
```bash
$ git clone -b <branch-name> <github-url>
```
#### HTTPS URL
```bash
$ git clone -b master https://github.com/sree298/git-demo.git
```
#### SSH URL
```bash
$ git clone -b master git@github.com:sree298/git-demo.git
```
### GIT Work flow for New Repo (init)
#### Create a new directory
```bash
$ mkdir git-demo
```
#### Navigate to git-demo directory
```bash
$ cd git-demo
```
#### set user-name and email-id (One time configuration only)
```bash
$ git config --global user.name "sree"
$ git config --global user.email "sree@gmail.com"
``
#### Create the new local-repo
$ git init
#### Check the status of changes
$ git status
#### Check the last 5 commits
$ git log -n 5
#### add the new file
$ vi ram.txt
M1
#### add/move the file to staging area
$ git add ram.txt
#### Commit the chnages
$ git commit -m "M1"
#### Check the last 5 commits
$ git log -n 5
#### add remote GITHUB repo
#### SSH URL
$ git remote add origin git@github.com:futuretechdevops/git-demo.git
#### HTTPS URL
$ git remote add origin https://github.com/futuretechdevops/git-demo.git
#### Verify the git remote details
git remote -v
#### push the code to remote repo (Github)
git push origin master

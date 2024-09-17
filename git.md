# Git
<!-- TOC -->
* [Git](#git)
  * [Basic git commands](#basic-git-commands)
    * [Setup](#setup)
  * [Advanced git commands](#advanced-git-commands)
<!-- TOC -->

## Basic git commands

### Setup
```shell
# Setup global
git config --global user.name "FIRST_NAME LAST_NAME"
git config --global user.email "MY_NAME@example.com"
git config --global init.defaultBranch main

#Setup repository-specific
git config user.name "FIRST_NAME LAST_NAME"
git config user.email "MY_NAME@example.com"
```

## Advanced git commands

Commit executable file
```shell
git add --chmod=+x <fileName>
```

Remove file from all commits in history
```shell
git filter-branch --tree-filter 'rm -f <filename>' HEAD
```

Move subfolder history to separate branch 
```shell
git subtree split -P <name-of-folder> -b <name-of-new-branch>
```

Show all records when branches and other references were updated (even deleted branches)
```shell
git reflog
```

Commit changes in `.gitignore` file
```shell
git rm -rf --cached .
git add .
git commt -m "Message"
```

Specific SSH key
```shell
# Push
GIT_SSH_COMMAND='ssh -i ~/.ssh/id_rsa_myrsa' git push origin main
# Or we could edit .git/config file in our repo and add sshCommand for [core]
[core]
  sshCommand = "ssh -i ~/.ssh/id_rsa_myrsa"
```
# Git Version Control System

Git is a version control system for tracking changes in computer files and coordinating work on those files among multiple people.

## Contents

- [Commands](#commands)
  - [Cloning](#cloning)
  - [Dates](#dates)
  - [Fetch](#fetch)
- [Links](#links)

## Commands

Clone a specific repository

```
$ git clone <URL>
```

### Cloning

#### Clone specific commit or branch

Git commands for cloning an existing repository to a specific commit or branch.

#### Clone repository to a specific commit

Create empty repository to store the content:

```
$ git clone <URL>
$ git reset <SHA-1> --hard
```

#### Clone single branch

```
git clone <URL> --branch <BRANCH> --single-branch <FOLDER>
```

#### Clone only latest commit from a given branch

```
git clone <URL> --depth=1 --branch <BRANCH> --single-branch <FOLDER>
```

#### Shallow clone a specific commit with depth 1

Instead of clone use the fetch command:

```
git fetch origin <SHA-1>
```

### Dates

#### Set the date of the last commit to the current date

```
$ GIT_COMMITTER_DATE="$(date)" git commit --amend --no-edit --date "$(date)"
```
  
#### Set the date of the last commit to a specific date

```
$ GIT_COMMITTER_DATE="Mon 20 Jul 2019 01:59:20 BST" git commit --amend --no-edit --date "Mon 20 Jul 2019 01:59:20 BST"
```

More info at [https://codewithhugo.com/change-the-date-of-a-git-commit/](https://codewithhugo.com/change-the-date-of-a-git-commit/)


### Fetch

#### Pull a certain branch

Fetch the remote branch:

```
$ git fetch origin <BRANCH-NAME>
```

Merge it into the current branch:

```
$ git merge origin/<CURRENT-BRANCH>
```

* Fix merge conflicts, if they occur
* Add merge conflict fixes

Commit the merge:

```
$ git commit
```

## Links

- [How to git push without conflict on diverge branch](https://stackoverflow.com/questions/20512468/how-to-git-push-without-conflict-on-diverge-branch) - StackOverflow
- [Why I love Trunk Based Development (or pushing straight to master)](https://medium.com/@mattia.battiston/why-i-love-trunk-based-development-641fcf0b94a0)

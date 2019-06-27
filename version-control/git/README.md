# Git Version Control System

Git is a version control system for tracking changes in computer files and coordinating work on those files among multiple people.

## Contents

- [Commands](#commands)
  - [Clone specific commit or branch](#clone-specific-commit-or-branch)
- [Links](#links)

## Commands

Clone a specific repository

```
$ git clone <URL>
```

### Clone specific commit or branch

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

## Links

- [How to git push without conflict on diverge branch](https://stackoverflow.com/questions/20512468/how-to-git-push-without-conflict-on-diverge-branch) - StackOverflow

# Git notes and commands

## Table of contents

- [What is Git?](#what-is-git)
- [How Git works](#how-git-works)
- [Steps to create a new GitHub repository](#steps-to-create-a-new-github-repository)
- [Git commands](#git-commands)

## What is Git?

Git is a DevOps tool used for source code management. It is a free and open-source version control system used to handle small to very large projects efficiently. Git is used to tracking changes in the source code, enabling multiple developers to work together on non-linear development.

### Benefits of Git

- Every developer has an entire copy of the code on their local system.
- Any changes made to the source code can be tracked by others.
- There is regular communication between the developers.
- Code files can be reverted to previous states.

## How Git works

Git works by storing projects within a repository and tracking any changes or updates in the repository code. These repositories can either be on the local machine or on remote platforms such as GitHub or Bitbucket.

Working on a project using Git involves a workflow of various stages. This workflow starts within the working directory where the project code is changed. Once the code changes are finished within a file, the changes can be staged. This means that they are ready to be commited to the repository and implemented.

Once all the necessary code changes are done in all the code files, the files in the staging area can be commited and then pushed to the remote repository.

A branching system allows developers to create an isolated environment where they can work on a copy of the original code to fix bugs or develop new features. These changes don't affect the main branch until the branch is merged with it. This is done to keep the main branch as the stable version of the project.

Git can be instructed to not track certain files by using a **_.gitignore_** file. This file contains a list of all files that should be ignored and not tracked by Git. A collection of useful .gitignore template files provided by GitHub can be found [here](https://github.com/github/gitignore).

## Steps to create a new GitHub repository

An SSH key must be created and added to the GitHub account to allow connections to remote repositories. This can be done by following the instructions [here](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account).

1. Press the 'Create a new repository' button on the GitHub interface.

2. Give the repository a name and choose if it is a private or public repo. Do not add the README,.gitignore or license files at this stage.

3. Create a local directory and repository using the command line.

```
mkdir <directory> && cd <directory>
git init
```

4. Create the **_README.md_** and **_.gitignore_** files.

5. Connect to the remote repository.

```
git remote add origin git@github.com:<username>/<repo-name>.git
```

6. Create the **_main_** branch.

```
git branch -M main
```

7. Push the local repository to the new remote repository on GitHub.

```
git push -u origin main
```

## Git commands

### Repository configurations

| Command                                                                     | Description                                        |
| --------------------------------------------------------------------------- | -------------------------------------------------- |
| `git init`                                                                  | Creates a new repository in the current directory. |
| `git clone ssh://git@github.com/<username>/<repo-name>.git`                 | Clones a remote repository on the local machine.   |
| `git remote set-url origin ssh://git@github.com/<username>/<repo-name>.git` | Change remote repository url                       |

### Staging

| Command              | Description                                                       |
| -------------------- | ----------------------------------------------------------------- |
| `git status`         | Displays the state of the working directory and the staging area. |
| `git add <filename>` | Adds the file or directory to the staging area.                   |
| `git rm <filename>`  | Removes the file or directory from the staging area.              |

### Changes

| Command | Description |
| `git diff` | Shows differences between files that are not staged yet |
| `git diff -staged`| Shows difference between files in the staging area and the latest version |
| `git diff <branch-1> <branch-2>` | Differences between the two branches |

### Commiting

| Command                               | Description                                                                                                         |
| ------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| `git commit -m "Commit message here"` | Commits any staged files and adds a short message that briefly describes the changes.                               |
| `git log [--summary] [--oneline]`     | Outputs a log of all commits made, including the commit ID and message.                                             |
| `git revert <commit_ID>`              | Reverts the repository to the commit specified by the ID. Does not delete the commits made after the specified one. |
| `git reset <commit_ID>`               | Same as the revert command but deletes all commits made after the specified commit.                                 |

### Updating changes

| Command     | Description                                                                      |
| ----------- | -------------------------------------------------------------------------------- |
| `git fetch` | Checks for updates in the remote repository.                                     |
| `git pull`  | Same as the fetch command but downloads any new changes to the local repository. |
| `git push`  | Uploads the changes made on the local repository to the remote repository.       |

### Branches

| Command                                                             | Description                                     |
| ------------------------------------------------------------------- | ----------------------------------------------- |
| `git branch`                                                        | View all branches in the repository.            |
| `git branch <branch-name>`                                          | Creates a new branch with the given name.       |
| `git branch -D <branch-name>`                                       | Deletes the local branch.                       |
| `git branch -m <current-name> <new-name>`                           | Rename a local branch                           |
| `git branch --track <new-local-branch> origin/<remote-base-branch>` | New local branch based on the remote branch.    |
| `git push origin`                                                   | Pushes the named branch to GitHub.              |
| `git push --delete origin/<remote-branch-name>`                     | Deletes a remote branch.                        |
| `git merge <source-branch> <target-branch>`                         | Merge the source branch into the target branch. |
| `git checkout <branch-name>`                                        | Switch to the named branch.                     |

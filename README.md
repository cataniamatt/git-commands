# Git Notes

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

Files can be ignored by Git by creating a **_.gitignore_** file. This file contains a list of all files that should be ignored and not tracked by Git. A collection of useful .gitignore template files provided by GitHub can be found [here](https://github.com/github/gitignore).

## Git commands

### Creating/cloning repositories

| Command                                                           | Description                                        |
| ----------------------------------------------------------------- | -------------------------------------------------- |
| `git init`                                                        | Creates a new repository in the current directory. |
| `git clone ssh://git@github.com/[username]/[repository-name].git` | Clones a remote repository on the local machine.   |

### Staging

| Command              | Description                                                       |
| -------------------- | ----------------------------------------------------------------- |
| `git status`         | Displays the state of the working directory and the staging area. |
| `git add [filename]` | Adds the file or directory to the staging area.                   |
| `git rm [filename]`  | Removes the file or directory from the staging area.              |

### Commiting

| Command                               | Description                                                                                                         |
| ------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| `git commit -m "Commit message here"` | Commits any staged files and adds a short message that briefly describes the changes.                               |
| `git log`                             | Outputs a log of all commits made, including the commit ID and message.                                             |
| `git revert [commit ID]`              | Reverts the repository to the commit specified by the ID. Does not delete the commits made after the specified one. |
| `git reset [commit ID]`               | Same as the revert command but deletes all commits made after the specified commit.                                 |

### Updating changes

| Command     | Description                                                                      |
| ----------- | -------------------------------------------------------------------------------- |
| `git fetch` | Checks for updates in the remote repository.                                     |
| `git pull`  | Same as the fetch command but downloads any new changes to the local repository. |
| `git push`  | Uploads the changes made on the local repository to the remote repository.       |

# Gitting around

## Story

This project is about familiarizing yourself with git. It involves moving around in a repository with multiple branches (you do not need to create these) to solve different tasks. Solving these tasks may give confidence in your knowledge of git repository structure and of using the more advanced features for profit.

To be able to solve the exercises you first need to learn how to list branches and how to switch to them as the exercises for the tasks can be found on separate branches.

## What are you going to learn?

- Use git history.
- Understand git branch structure.
- Use basic shell commands.

## Tasks

1. Set up passwordless git access on your computer and GitHub account by using `SSH`. This means that you use SSH (Secure Shell Protocol) to authenticate to GitHub instead of giving your username and password.
    - Executing `git config --get remote.origin.url` in shell on the repo
 shows a response that starts with: `git@...`
    - Executing `git fetch` in shell on the repo does not ask for username and password.

2. Initialize your repository by running the initialization script, `bash ./helper/init`. This will create branches needed for the following tasks.
    - Executing the `git branch` command in shell returns the following output.
```
collect-files
find-secret
* development
remote-change
resolve-conflict
size-history
```

3. Switch to the `remote-change` branch and pull the changes from the remote.
    - After executing `git checkout remote-change`, executing `git log` shows a new merge commit starting with: "Merge branch 'remote-change' ..." on the top of the output.
    - After executing `git checkout remote-change` executing `git status` shows the following output.
```
On branch remote-change
Your branch is ahead of 'origin/remote-change' by 2 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
```

4. Switch to the `resolve-conflict` branch, pull the changes from the remote and resolve conflicts.
    - After executing `git checkout resolve-conflict`, the contents of `work.txt` should look like:
```
I work
I rest after I work
```
    - After executing `git checkout resolve-conflict` the git log shows a new merge commit starting with the following line.
"Merge branch 'resolve-conflict' ..."

5. Find the secret about the meaning of 42 by investigating the git history of the `find-secret` branch. Experiment with some `git` commands to see what has changed in the previous commits.
    - Knowledge of what 42 means in programming.

6. On the `size-history` branch there are multiple commits changing the `names.txt` file. Find all versions of `names.txt` and the size (in bytes) for each version. Collect all sizes of `names.txt` separated by commas in a new `result.txt` file starting with the oldest, then commit your changes. You should visit all previous commits of this repository and observe the size of a changing file.
    - Executing `git log --name-only` after executing `git checkout size-history` shows a new commit adding `result.txt`.
    - The commit message is meaningful and describes the change accurately.
    - Executing `cat result.txt` after executing `git checkout size-history` in the shell shows a 5 elements list starting with 35, ending with 89

7. On the `collect-files` branch there were several files created, some still exist. Find the names of all files that ever existed on the branch, collect all the names separated by commas in a new `result.txt` file, then commit your changes. You should visit all previous commits of this repository and observe which files exist.
    - After executing `git checkout collect-files`, the last commit message is meaningful and describes the change accurately.
    - Executing `git log --name-only` after executing `git checkout collect-files` shows a new commit adding `result.txt`.
    - Executing `cat result.txt` after executing `git checkout collect-files` in the shell shows 14 (or 16 if `.` and `..` are included) lines.

## General requirements

None

## Hints

- Always make sure that you are on the correct branch when working on an exercise.
- Use `git log --oneline` for a succinct view of the history of the current branch.

## Background materials

- <i class="far fa-exclamation"></i> [Moving around branches](https://www.atlassian.com/git/tutorials/using-branches/git-checkout)
- <i class="far fa-exclamation"></i> [Branches in a nutshell](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell)
- <i class="far fa-exclamation"></i> [Bash commands and arguments](https://mywiki.wooledge.org/BashGuide/CommandsAndArguments)
- <i class="far fa-book-open"></i> [Bash pattern matching](https://mywiki.wooledge.org/BashGuide/Patterns)


# Git Advanced Workshop

A hands-on workshop for learning some advanced Git version control.

## Purpose

This workshop walks through additional Git concepts and commands using several worked concepts. Given that you've been working as 

- Initializing and cloning repositories
- Reflogs
- Merging vs rebasing and resolving conflicts
- Undoing changes (reset, revert, checkout)
- Git worktrees

## Prerequisites

- Git installed (`git --version` to verify)
- A terminal / command-line environment
- A text editor of your choice

## How to Use This Repo

The file `story.txt` serves as the shared working file for all exercises. Each scenario will ask you to make changes to it, stage those changes, and practice various Git operations.

Follow the instructor's prompts or work through the exercises at your own pace.

### Tasks
1. Add a Chapter 2 commit, with its own commit message with the following text: "Some text"
2. Add a new branch, task-2. On this branch, Add an additional sentence to Chapter 2, and include it in your previous Chapter 2 commit
3. Combine the Chapter 1 & Chapter 2 commits, and change the commit message to reflect things
4. On `main`, add a Chapter 3 with the text: "They discovered the reflog and realised nothing is ever truly lost." Commit it, then use `git reset --hard HEAD~1` to remove it. Recover the commit using `git reflog`
5. Create a branch `task-5` from `main`. On `main`, change the Chapter 1 text to "The developers boldly typed their first command." On `task-5`, change it to "The developers nervously typed their first command." Merge `task-5` into `main` and resolve the conflict
6. You've just realised the commit from Task 4 has a typo — "realised" should be "realized" (American English). Use `git rebase -i` to edit that specific commit, fix the typo, and continue the rebase
7. Run `git log --oneline` and review the history. Use an interactive rebase to reorder the commits so that all chapter additions appear in chronological order
8. Create a branch `task-8` and make three small commits (one word change each). Use `git rebase -i` to squash all three into a single commit with a meaningful message, then merge it back into `main`
9. Use `git worktree add ../git-workshop-hotfix hotfix` to create a new worktree on a `hotfix` branch. In that worktree, change the opening line of `story.txt` to "Once upon a time, in a land of *distributed* version control," and commit it. Switch back to the original worktree, merge `hotfix` into `main`, then clean up with `git worktree remove ../git-workshop-hotfix`
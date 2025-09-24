# Git Exercises - Answers

## Exercise 1

### Question 3a: What is the .git directory used for?
The `.git` directory is Git's internal database. It stores all the commit history, configuration, branches, and pointers. It's created by the `git init` command and should never be edited manually.

### Question 6a: In which stage does the file appear?
After using `git add`, the file appears in the **staging area** (also called the index). This means it is prepared to be saved in the next commit.

### Question 11b: Why does diff give no output after add? How to see staged diff?
After `git add`, the changes are staged. Use `git diff --staged` or `git diff --cached` to see changes in the staging area.

## Exercise 2

### Question 6a & 6b: What happens when switching branches?
When switching back to master, the commits made in the branch don't appear in the log, and files revert to their original state because each branch maintains its own version of the code.

### Question 8a, 8b, 8c: What is a fast-forward merge?
A fast-forward merge happens when the target branch hasn't diverged. Git simply moves the branch pointer forward. No merge commit is created, and the history remains linear.

### Question 12: What is a merge commit?
When branches have diverged, Git creates a merge commit that joins the two histories. This appears as a fork and re-join in the commit graph.

## Exercise 3

### Question 6b & 6c: What happens with git checkout -- file?
`git checkout -- file` discards unstaged changes in the working directory, reverting the file to its last committed state. The HEAD pointer doesn't move.

### Question 8a, 8b, 8c: What does git revert do?
`git revert` creates a new commit that undoes the changes of a previous commit. It's safe for shared history because it doesn't rewrite existing commits.

### Question 10b, 10c, 10d: What does git reset --soft do?
`git reset --soft` moves the branch pointer back but keeps changes staged. The commit is temporarily lost but changes are ready to recommit.

### Question 11a, 11b: What does git reset (default) do?
Default `git reset` unstages changes but keeps them in the working directory. It uses HEAD as default scope.

### Question 12a, 12b, 12c: What does git reset --hard do?
`git reset --hard` discards all uncommitted changes and resets working directory to the last commit. It uses HEAD as default and can cause permanent data loss.

## Exercise 4

### Question 6a: What do you think rebase is doing? Which branch will be the base?
Rebase reapplies commits from the current branch onto another branch. The main branch will be the base.

### Question 6c: What has changed?
The commit history changed from forked to linear. Feature branch commits now appear after main branch commits.

### Question 6d: What's the difference between this and merging?
Merge preserves fork history with a merge commit. Rebase creates clean linear history by moving commits.

### Question 9a, 9b, 9c: What does the graph look like after rebase?
After rebase, the graph is linear. Changes are combined by replaying commits sequentially. Unlike merge, there's no fork-join structure.

### Question 11b: What does squashing do to the commit history?
Squashing combines multiple commits into one, creating cleaner history with fewer, more meaningful commits.
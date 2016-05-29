---
layout: post
title:  "Basic git command"
categories: git
subcategory: beginner
---
# Display git log
Display git log information nicely
`git log --oneline --decorate --graph`


where `oneline` show commit in one line, `--decorate` give some color and
`--graph` gives graph show.


# Display git branches
* Show all locals and remote branchs
  `git branch -a`

* Show all locals branchs only
  `git branch`

* Show all remote branchs only
  `git branch -r`

# Remove/delete git branch
You can remove either local or remote branch

## Removing local branch
Let you want to delete your locale branch named `foo`
  `git branch -d foo`

If branch `foo` have un merged commit then it need to force delete
  `git branch -D foo`

## Removing remote branch
You can also use one of the following methods to delete the remote branch.
Let you want to delete remote branch `bar`
`git push --delete origin bar`

Which does the same thing as

`git push origin :serverfix`
but it may be easier to remember.

# Create and checkout to new branch:
`git checkout -b feature/profile-image-crop`

# Show last git commit
* `git show --summray`
  this will show commit message
* `git show --stat`
  this also show last git commit with change file list

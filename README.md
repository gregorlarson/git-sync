# git-sync script
Push and merge with multiple remote repositories

This script provides an automatic fetch, merge and push with multiple git remotes. It allows you to have multiple remotes and even *push* to non-bare repos.

# Usage
Simply type:

    git-sync

# Safety
git-sync does not force any push or fetch, so, it is quite safe to use on any repo.

- git-sync does, however, push without asking, so, if you have a repo that you have push permission to, but, don't  want to push from this working tree, then you can prevent that by doing:

    git config remote.{remotename}.syncto no
    
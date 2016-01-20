# git-sync script
Push and merge with multiple remote repositories

This script provides an automatic fetch, merge and push with multiple git remotes. It allows you to have multiple remotes and even *push* to non-bare repos.

# Usage
Simply type:

    git-sync

# Safety
git-sync does not force any push or fetch, so, it is quite safe to use on any repo.

- git-sync does, however, push without asking, so, if you have a repo that you have push permission to, but, don't  want to push from this working tree, then you can prevent that by doing:

    - `git config remote.{remotename}.syncto no`

- this will stop git-sync pushing to that remote (substitute {remotename} with the actual remote).

# Configuration Settings
Notation note: {some-field} implies that you need to fill in the actual value `without the {}`.

## remote.{remote-name}.sync
- set to NONE in order to stop git-sync using that remote. For example:
    - git config remote.repo2.sync NONE
        - git-sync with repo2 is disabled
    - git config --unset remote.repo2.sync
        - git-sync with repo2 is re-enabled (default)

## branch.{local-branch-name}.sync
Set a default remote branch-name to use with your local branch, for example:
```
git config branch.master.sync synced/master
```
- this would push/push from {remote}/synced/master for some compatibility with git-annex.

## remote.{remote-name}.sync
Set a prefix for syncing to a certain remote, or, disable syncing with that remote (by setting to NONE).

### branch.{local-branch-name}.{remote-name}-sync
Like remote.{remote-name}.sync above, but applies only to a certain remote.

## remote.{remote-name}.syncto
Disable push to a specific remote by setting to no.

## remote.{remote-name}.syncfrom
Disable fetch and merge from a specific remote by setting to no.



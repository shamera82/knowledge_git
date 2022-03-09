## Renaming Git Branch #
Follow the steps below to rename a Local and Remote Git Branch:

#### If you want to rename a branch while pointed to any branch, do:

``` git branch -m <oldname> <newname> ```

#### If you want to rename the current branch, you can do:

``` git checkout <old_name> ```

#### Rename the local branch by typing:

``` git branch -m <new_name> ```

At this point, you have renamed the local branch.

If you’ve already pushed the <old_name> branch to the remote repository , perform the next steps to rename the remote branch.

#### Push the <new_name> local branch and reset the upstream branch:

``` git push origin -u <new_name> ```

#### Delete the <old_name> remote branch:

``` git push origin --delete <old_name> ```

#### A way to remember this is -m is for "move" (or mv), which is how you rename files. Adding an alias could also help. To do so, run the following:

``` git config --global alias.rename 'branch -m' ```

#### If you are on Windows or another case-insensitive filesystem, and there are only capitalization changes in the name, you need to use -M, otherwise, git will throw branch already exists error:

``` git branch -M <newname> ```

That’s it. You have successfully renamed the local and remote Git branch.

# Modify Commit
This readme shows how to modify the latest commit message and a specific commit message.

## Modify the Latest Commit
Please follow these steps to modify the commit message:

1. Check the git commits by typing `git log`.

![git log](./images/git_log.png "git log")

2. If you need to change the latest commit, follow these steps:
   - Use the command `git commit --amend`.

![git amend](./images/git_amend.png "git amend")

   - Now you can edit the commit message in your default editor.

![git amend_edit](./images/git_amend_edit.png "git amend_edit")

   - Save and exit. You will see the following git commit amend output:

![git_amend_output](./images/git_amend_output.png "git_amend_output")

   - Now, if you check `git log`, you will see the latest commit is updated with the changes.

![git log updated](./images/git_log_updated.png "git log updated")

   - Finally, push the modified commit to your remote branch. You may need to use `git push --force` to achieve this.

![git push](./images/git_force_push.png "git force push")


## Modify a Specific Commit
Please follow these steps to modify a specific commit message:

1. Check the git commits by typing `git log`.

![git log](./images/git_log.png "git log")

2. Assume you need to change the 3rd commit from the top (2b0b91911350beed31c167a05020763448a80c). In this case, you need to use git rebase as follows:

![git log commit](./images/git_log_commit.png "git log commit")

3. Use the command `git rebase --interactive 2b0b91e911350beed31c167a050207634e48a80c^`. Make sure to use the `^` symbol at the end; it's very important. If not, it shows up to the commit `2b0b91e911350beed31c167a050207634e48a80c`.

If you do it without `^` at the end of the commit ID, you will get the following output, where you can’t see the commit `2b0b91e911350beed31c167a050207634e48a80c`.

![git rebase not end with ^](./images/git_rebase_wrong.png "git rebase not end with ^")

Make sure to use `^` at the end of the commit ID. Then you can see the rebase message with the commit ID `2b0b91e911350beed31c167a050207634e48a80c` in short form as `Pick 2b0b91e file move`.

![git rebase end with ^](./images/git_rebase_correct.png "git rebase end with ^")

4. Now you can see commit ID `2b0b91e911350beed31c167a050207634e48a80c` in short form as `2b0b91e` in the first line. You need to change `Pick` to `edit`, then save and exit.

![git rebase edit](./images/git_rebase_edit.png "git rebase edit")

5. You will see this output. Now type `git commit --amend`.

![git rebase output](./images/git_rebase_output.png "git rebase output")

6. Edit the commit message, save, and exit.

![git_amend_with_new](./images/git_amend_with_new.png "git_amend_with_new")

7. You will see an output similar to the following:

![git_amend_output_new](./images/git_amend_output_new.png "git_amend_output_new")

8. Finally, to apply the commit message to your branch, type `git rebase --continue`.

![git_rebase_continue](./images/git_rebase_continue.png "git_rebase_continue")

9. Now, if you check the output of `git log`, you will see the 3rd commit message has been changed. You may also notice that the commit IDs from that commit to the latest have changed, and you can’t see the old commit IDs anymore.

![git_log_new_commit](./images/git_log_new_commit.png "git_log_new_commit")

10. Now you can force push the changes to the remote branch.

![git_push_force](./images/git_push_force.png "git_push_force")

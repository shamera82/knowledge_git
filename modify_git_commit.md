# Modify Commit
In this readme, shows how to modify latest commit message and specific commit message


## Modify latest commit
Please follow these steps to modify the commit message

1. check the git commits by typing `git log`

![git log](./images/git_log.png "git log")

2. if you need to change the 1st commit use following steps
   - use command `git commit --amend`

![git amend](./images/git_amend.png "git amend")

   - now you can edit the commit message in your default editor

![git amend_edit](./images/git_amend_edit.png "git_amend_edit")

   - save and exit. you can see the following git commit amend output

![git_amend_output](./images/git_amend_output.png "git_amend_output")

   - now if you look for `git log` you can see latest commit is updated with the changes.

![git log updated](./images/git_log_updated.png "git log updated")

   - finally push the modified commit to your remote branch. you may need to use `git push --force` to achieve this.

![git push](./images/git_force_push.png "git force push")




## Modify a specific commit
Please follow these steps to modify the commit message

1. check the git commits by typing `git log`

![git log](./images/git_log.png "git log")

2. assume need to change the 3rd commit from top (2b0b91911350beed31c167a05020763448a80c). in this case you need to use git rebase. as follows 

![git log commit](./images/git_log_commit.png "git log commit")

3. use command `git rebase --interactive 2b0b91e911350beed31c167a050207634e48a80c^` make sure to use `^`, it's very important. if not shows upto the commit `2b0b91e911350beed31c167a050207634e48a80c`

if you do it without `^` at the end of the commit id, you will get following output, which we can't see commit `2b0b91e911350beed31c167a050207634e48a80c`

![git rebase not end with ^](./images/git_rebase_wrong.png "git rebase not end with ^")

make sure to use `^` at the end of commit id, then u can see the rebase message with commit id `2b0b91e911350beed31c167a050207634e48a80c` in shortform as `Pick 2b0b91e file move`

![git rebase end with ^](./images/git_rebase_correct.png "git rebase end with ^")

3. now you able to see commit id `2b0b91e911350beed31c167a050207634e48a80c` in shortform as `2b0b91e` in 1st line. you need to change `Pick` to `edit`, then save and exit.

![git rebase edit](./images/git_rebase_edit.png "git rebase edit")

4. you can see this output, now type `git commit -amend`, 

![git rebase output](./images/git_rebase_output.png "git rebase output")

5. then edit the commit message, save and exit.

![git_amend_with_new](./images/git_amend_with_new.png "git_amend_with_new")

6. you can see output simillar to following output.

![git_amend_output_new](./images/git_amend_output_new.png "git_amend_output_new")

7. finaly to apply the commit message to your branch type `git rebase -continue`

![git_rebase_continue](./images/git_rebase_continue.png "git_rebase_continue")

9. now if you check output of git log, you can see 3rd commit message has been change. you may can notice the commit id's from that commit to latest also change and can't see old commit id anymore. 

![git_log_new_commit](./images/git_log_new_commit.png "git_log_new_commit")

10. now you can force push the changes to remote branch

![git_push_force](./images/git_push_force.png "git_push_force")


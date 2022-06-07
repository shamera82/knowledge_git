# Git Delete Branch
If you just want to learn the correct incantation to delete branches in Git, we’ll start by offering the TL

### To delete a local branch in Git, you simply run:

```
git branch -d <branch-name>
```

If the branch contains unmerged changes, though, Git will refuse to delete it. If you’re sure you want to do it, you’ll have to force the deletion by replacing the `-d` parameter with an uppercase `-D`

### Force delete branch

```
git branch -D <branch-name>
```

You don’t use the git branch command to delete a remote branch. You use git push, even if that sounds weird. Here’s how you do it:

### Delete remote branch

```
git push --delete <remote name> <branch name>
```

It’s like you’re pushing—sending—the order to delete the branch to the remote repository.

With that out of the way, we’ll now explore the deletion of branches in Git in some more depth.


### simple way
```
## delete local
➜  tf_azure_vm git:(master) git branch -d feature/fix-infra            
Deleted branch feature/fix-infra (was 75gy0a3).

## delete remote
➜  tf_azure_vm git:(master) git push origin --delete  feature/fix-infra                  
Enter passphrase for key '/Users/shamera/.ssh/id_rsa': 
To ssh.dev.azure.com:v3/shamera/cloud/tf_azure_vm
 - [deleted]         feature/fix-infra
➜  tf_azure_vm git:(master) 
```

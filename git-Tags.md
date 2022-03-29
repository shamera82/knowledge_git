## Tagging lets developers mark important checkpoints in the course of their projects' development. For instance, software release versions can be tagged. (Ex: v1.3.2) It essentially allows you to give a commit a special name(tag).

### To view all the created tags in alphabetical order:

``` git tag ```

### To get more information on a tag:

``` git show v1.4 ```

### There are two types of tags:
You can create two type of tags: annotated and lightweight. They first ones are compete objects in GIT database: they are checksummed, requiere a message (like commits) and store other important data such as name, email and date. On the other hand, lightweight tags don require a mesage or store other data, working just as a pointer to a specific point in the project.

#### Annotated
To create an anotated tag, add `-a` tagname `-m "tag message"` to the `git tag` command. As you can see, the -a specifies that you are creating an annotated tag, after comes the tag name and finally, the -m followed by the tag message to store in the Git database.

``` git tag -a v1.2 -m "my version 1.4" ```

#### Lightweight
Lightweight tags contain only the commit checksum (no other information is stored). To create one, just run the `git tag` command without any other options (the `-lw` characters at the end of the name are used to indicate lightweight tags, but you can mark them as you like). This time you didn’t specify a message or other relevant data, so the tag contains only the refered commit’s checksum.

``` git tag v1.2 ```

They differ in the way that they are stored.
These create tags on your current commit.

### Incase, you’d like to tag a previous commit specify the commit ID you’d like to tag:
You can also tag past commits using the `git tag` commit. In order to do this, you’ll need to specify the commit’s checksum (or at least a part of it) in the command’s line.

First, run git log to find out the required commit’s checksum:

```
$ git log --pretty=oneline
ac2998acf289102dba00823821bee04276aad9ca added products section
d09034bdea0097726fd8383c0393faa0072829a7 refactorization
a029ac120245ab012bed1ca771349eb9cca01c0b modified styles
da43a5f7389adcb9201ab0a289c389ed022a910b finished details
0adb03ca013901c1e02174924486a08cea9293a2 small fix in search textarea styles
```
When you have the checksum needed, add it at the end of the tag creation line:

``` git tag -a v1.2 9fceb02 ```

The tags names may be used instead of commit IDs while checking out and pushing commits to a remote repo.

### Push tags
Git does’t push tags by default when you run the git push command. So, to succesfully push a tag to a server you’ll have to git push origin command:

```
$ git push origin v4.0
Counting objects: 14, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (16/16), done.
Writing objects: 100% (18/18), 3.15 KiB | 0 bytes/s, done.
Total 18 (delta 4), reused 0 (delta 0)
To git@github.com:jcash/gitmanual.git
 * [new tag]         v4.0 -> v4.0
```

You can also use the `--tags` option to add multiple tags at once with the git push origin command:

```
$ git push origin --tags
Counting objects: 1, done.
Writing objects: 100% (1/1), 160 bytes | 0 bytes/s, done.
Total 1 (delta 0), reused 0 (delta 0)
To git@github.com:jcash/gitmanual.git
 * [new tag]         v4.0 -> v4.0
 * [new tag]         v4.1-lw -> v4.1-lw
```

### Checking out Tags
You can use git checkout to checkout to a tag like you would normally do. But you need to keep in mind that this would result a detached HEAD state.

```
$ git checkout v0.0.3
Note: checking out 'v0.0.3'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by performing another checkout.
```

### Checking out Tags to Branch
If you do this and make a commit, your version2 branch will be slightly different than your v2.0.0 tag since it will move forward with your new changes, so do be careful.
```
git checkout -b version2 v0.0.3
Switched to a new branch 'version2'
```

### Deleting a Tag
You may find a situation were you want to delete a certain tag. There’s a very useful command for this situations:

```
$ git tag --delete v0.0.2
$ git tag
v0.0.1
v0.0.3
v0.0.4
```

### Updating exsisting tag

Delete the tag on any remote before you push
```
git push origin :refs/tags/v0.0.4
```
Replace the tag to reference the most recent commit
```
git tag -fa v0.0.4 "this is the update tag"
```

Push the tag to the remote origin
```
git push origin master --tags
```

### Tag on a old commit
```
# add tag to specific commit 
git tag -a v1.2 9fceb02 -m "This is tag for the commit 9fceb02"

# push the tag to the remote repo
git push origin v1.2
```

This is all about git tagging. Enjoy !!!

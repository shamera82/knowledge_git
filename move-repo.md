### How to move repos from stash to git

#### stash repo

#### Step 1 : Create a Blank repository on Github without Readme.md
![ref log](https://github.com/shamera82/knowledge_git/blob/main/images/create-github-repo-without-any-readme-files.jpg.png?raw=true)

#### Step 2 : Moving all code and content from bitbucket
1. Check out the existing repository from Bitbucket:
```
git clone https://padm701@stash.auckland.ac.nz/scm/itspsr/uoatools.git
```
2. Now adding new GitHub Repository as upstream remote of the repository which is clone from bitbucket.
```
cd uoatools/
git branch -a
git remote add upstream http://psoftgitserver.uoa.auckland.ac.nz:3000/padm701/uoatools.git
```
3. push all branches and tags to GitHub Repository using below commands
```
git push upstream dev
git push --tags upstream
```
#### Step 3 : Add URL of New Github Repository as redirect URL
```
git remote set-url origin http://psoftgitserver.uoa.auckland.ac.nz:3000/padm701/uoatools.git
```
#### Step 4: At last Clone all branches and tags to GitHub Repository
```
git push --mirror
```

example:
```sh
git clone https://padm701@stash.auckland.ac.nz/scm/itspsr/uoatools.git
cd uoatools/
git branch -a
git remote add upstream http://psoftgitserver.uoa.auckland.ac.nz:3000/padm701/uoatools.git
git push upstream dev
git push --tags upstream
git remote set-url origin http://psoftgitserver.uoa.auckland.ac.nz:3000/padm701/uoatools.git
git push --mirror
git checkout prod
git push --mirror
git checkout test
git push --mirror
cd ..


E:\psoftgitserver\bin\gitea dump -c E:\psoftgitserver\custom\conf\app.ini

cd /apps/uoatools
git status
BRANCH=$(git status | grep "# On branch" | awk -F' ' '{print $4}')
echo $BRANCH
cd /apps
ls -ltr
mv uoatools uoatools_bakup_$(date -I);
ls -ltr
git clone http://user:pass@psoftgitserver.uoa.auckland.ac.nz:3000/ITSPSR/uoatools.git
cd uoatools
git status
git checkout $BRANCH
git status
vim /apps/uoatools/.git/config
```

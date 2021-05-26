# Git and Github

[TOC]

## Workflow for create new repo locally and remotely

* Create a new repository on Github

* Open terminal and create a new project folder

* Initialize the new project folder with `git`

```
git init
```

* Add files included in this new project folder

```
git add .
```

* Commit the files staged in local repository

```
git commit -m "First commit"
```

* Copy the remote repository URL and connect it with local repo

```
git remote add origin remote <repository URL>

# After build the connect, you need to double check if it sucessed.
# Use git remove -v to verifies the new remote URL
git remote -v

```

* Push the changes in your local repository to Github

```
git push -u origin master
```
or set master branch as the upstream branch

```
git push --set-upstream origin master
```
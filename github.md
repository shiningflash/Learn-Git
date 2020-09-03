Introduction to Git and Github
==============================
------------------------------------
## Introduction to GitHub
------------------------------------
(Github Inc. is United States-based company that provides hosting for software developers and version control system using Git)

------------------------------------

There are various remote repository hosting sites:

[GitHub](https://github.com), [BitBucket](https://bitbucket.org/), [Gitlab](http://www.gitlab.com/).

[Create a new github account](https://github.com/join)

[Create a new repository](https://docs.github.com/en/github/getting-started-with-github/create-a-repo)

------------------------------------
## Basic Command
### git clone
** *To download a copy of the remote repository from github on to the local machine* **
```sh
~$ git clone https://github.com/username/repository_name.git
```

### git push
__(push the changes to github repository)__

** *Now, go to the repository using [cd repository_name], do some change in any file, say README.md using [gedit README.md], Then commit it using [git commit -a -m "some messages"] and then push the changes to github repository using the following command* **
```sh
~$  git push
```
** *give username and password. The ```git push``` command collects all the snapshot we have made in the local repository and sends them to the remote repository.* **

### git pull
__(To retrieve all new changes from the github repository, use the git pull command)__
```sh
~$ git pull # give username and password
```
-----------------------------------
| Command | Explanation |
| ------- | ----------- |
| git clone ```<URL>``` | used to clone a remote repository into a local workplace |
| git push | commits from your local repo to a remote repo |
| git pull | fetch the newest updates from a remote repo |
-----------------------------------
#### Avoid providing username and password each time:
1. __SSH Key-Pair__ (stores the public key in our profile, so that github recognizes our computer)
[procedure here](https://docs.github.com/en/github/getting-started-with-github/create-a-repo)

2. __Credential Helper__ (cashes are credential for timed windows so that we don't need to give a password in every interaction). (this cache will work for 15 minutes)
    ```sh
    ~$ git config --global credential.helper cache
    ```
------------------------------------------------

## Using remote repository
```sh
~$ git remote -v
```
* it shows two links
    * origin  https://github.com/<username>/<repo_name>.git (fetch)
    * origin  https://github.com/<username>/<repo_name>.git (push)

    ** *One is to fetch data from the repository (__fetch__ ```URL``` use the ```HTTP``` for READ ONLY ACCESS) and the other one is push data to the remote repo (__push__ ```URL``` use the ```HTTPs``` for ACCESS CONTROL).* **
```sh
~$ git remote show origin # to get more information
~$ git branch -r # to get all branches (these are read only)
```
** *If we want to make any changes to a remote branch, we have to pull the branch, merge it with the local branch, then push it back to the origin.* **

### Fetching new changes + update local repo
__git fetch vs git pull:__ `git fetch` only fetches / retrieves the remote updates, but doesn't merge; ``git pull`` instantly merges all the remote updates. git pull: fetch + merge.
```sh
# to fetch all the updates of the remote repo
~$ git fetch
```
```sh
# to merge (update) all the new updates of the remote repo
~$ git pull
```
------------------------------------
| Command | Explanation |
| ------- | ----------- |
| git remote | lists remote repos |
| git remote -v | lists remote verbosely |
| git remote show ```<name>``` | describes a single remote repo |
| git remote update | fetches the most up-to date objects |
| git fetch | download remote branches from the remote repos without merging the content automatically |
| git branch -r | lists all remote branches |
----------------------------------------
### Solving conflicts
__git rebase:__ `git rebase` is an alternative of `git merge`. Rebasing instead of merging rewrites history and maintains linearity, making for cleaner code and also helps in identifying bugs.

__Best practices for collaboration:__
* Always synchronize your branches before starting any work of your own.
* Avoid having very large changes that modify a lot of different things.
* When working on a big change, it makes sense to have a separate feature branch.
* Have the latest version of the projects on the master branch and the stable version of the project on a separate branch.
* __Having good commit messages is important.__

##### Forking
A way of creating a copy of the given repository so that it belongs to our user.

##### Pull Request
A commit or series of commits that you send to the owner of the repository so that they incorporate in their tree.

##### workflow:
--------------
**fork the repo** you want to work on or change or edit
|
**clone the forked** repo to your local directory
|
go to the local directory (then check log and so on)
|
**add a new branch and shift** to it
```(git checkout -b <branch-name>)```
|
now change or add any file to the branch, add it and then commit
|
**create corresponding remote branch and push** the changes to it
```(git push -u origin <branch-name>)```
---------

##### Squash
Squash is a git option to collapse all the incremental commits in your pull request into a single commit. If you use Github interface, it will squash all your commits into one. Then it will give you the option to edit the commit message.

##### Managing projects

* It's important that you understand any changes you accept.
* Use a **Issue Tracker** so that you can learn about who is working on what and you can manage them easily.
* Use **Bug Tracker** to track bugs in your project (popularly used - ``Bugzilla``).
* Use **Issues** and you can assign anyone with the issues to fix. And, when you are fixed with the issues, add ```'Closes #<issue_id>'``` (eg, Closes #1) at the last of the commit message, so that the issue will be automatically deleted from the Issues.

##### some advice:
* reply promptly to pull-requests
* understand any changes you accept
* use an issue-tracker

----------------------------------------
#### Also check:
* [Before Version Control](https://github.com/shiningflash/learn-git/blob/master/before_version_control.md)
* [Git Command](https://github.com/shiningflash/learn-git/blob/master/git.md)

Introduction to Git and Github
==============================
------------------------------------
### Introduction to GitHub
------------------------------------
(Github Inc. is United States-based company that provides hosting for software developers and version control system using Git)

------------------------------------

There are various remote repository hosting sites:

[GitHub](https://github.com), [BitBucket](https://bitbucket.org/), [Gitlab](http://www.gitlab.com/).

[Create a new github account](https://github.com/join)

[Create a new repository](https://docs.github.com/en/github/getting-started-with-github/create-a-repo)

------------------------------------
### Basic Command
#### git clone
** *To download a copy of the remote repository from github on to the local machine* **
```sh
~$ git clone https://github.com/username/repository_name.git
```

#### git push
__(push the changes to github repository)__

** *Now, go to the repository using [cd repository_name], do some change in any file, say README.md using [gedit README.md], Then commit it using [git commit -a -m "some messages"] and then push the changes to github repository using the following command* **
```sh
~$  git push
```
** *give username and password. The ```git push``` command collects all the snapshot we have made in the local repository and sends them to the remote repository.* **

#### git pull
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
##### Avoid providing username and password each time:
1. __SSH Key-Pair__ (stores the public key in our profile, so that github recognizes our computer)
[procedure here](https://docs.github.com/en/github/getting-started-with-github/create-a-repo)

2. __Credential Helper__ (cashes are credential for timed windows so that we don't need to give a password in every interaction). (this cache will work for 15 minutes)
    ```sh
    ~$ git config --global credential.helper cache
    ```
------------------------------------------------

### Using remote repository
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

#### Fetching new changes + update local repo
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
#### Also check:  [Before Version Control](https://github.com/shiningflash/learn-git/blob/master/before_version_control.md)  [Git Command](https://github.com/shiningflash/learn-git/blob/master/git.md)

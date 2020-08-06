Introduction to Git and Github
==============================
--------------------------------
Before Version Control
----------------------
--------------------------------
```sh
# creating and opening two file (in Linux)
~$ touch a.py b.py
~$ gedit a.py b.py
```
```sh
# to see files
~$ ls -l
~$ ls -la # files with .extension
```
```sh
# differing files (Linux)
~$ diff a.py b.py
~$ diff -u a.py b.py # more specific
~$ diff -u a.py b.py > change.diff # save changes to another file
~$ cat change.diff # to check the file
~$ patch a.py < change.diff # apply changes to a.py
```
#### run source code (Bonus)
**C++:**
```sh
~$ g++ -o <any_name> <file_name>.cpp
~$ ./<any_name>
```
**py:**
```sh
~$ python <file_name>.py
```
**java:**
```sh
~$ javac <file_name>.java
~$ java <file_name>
```
----------------------------------------
#### Also check:  [Git Command](https://github.com/shiningflash/learn-git/blob/master/git.md) [Github Command](https://github.com/shiningflash/learn-git/blob/master/github.md)

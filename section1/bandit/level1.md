Bandit Level 0 → Level 1
========================

### <font color="grey">Level Goal</font>

The password for the next level is stored in a file called **readme** located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH to log into that level and continue the game.

### <font color="grey">Commands you may need to solve this level</font>

ls, cd, cat, file, du, find

### Solution

Account: bandit1

Password: boJ9jbbUNNfktd78OOpsqOltutMc3MY1

Host: bandit.labs.overthewire.org

Use the password from level0, list as above.

```
$ ssh bandit1@bandit.labs.overthewire.org -p 22
...
bandit9@bandit.labs.overthewire.org's password:
boJ9jbbUNNfktd78OOpsqOltutMc3MY1
```

There is a file named as -. <br>
In Linux, dash means stdin/stdout, so we have to use absolute path or relative path.

```
$ cat /home/bandit1/-
CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9

$ cat ./-
CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9
```

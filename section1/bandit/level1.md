Bandit Level 0 → Level 1
========================

### <font color="grey">Level Goal</font> ###

The password for the next level is stored in a file called **readme** located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH to log into that level and continue the game.

### <font color="grey">Commands you may need to solve this level</font> ###

ls, cd, cat, file, du, find

### Solution ###

> Account: bandit0 <br />
> Password: bandit0 <br />
> Host: bandit.labs.overthewire.org

Use the password from level0, list as above.

```
$ ssh bandit0@bandit.labs.overthewire.org -p 22
...
bandit9@bandit.labs.overthewire.org's password:
bandit0
...
```

首先用本關卡建議的 ls 指令檢查一下 家目錄 (home directory) 的檔案清單列表，有一個 readme 檔案和其他的 Bash Startup Files 。

```
bandit0@melinda:~$ ls -al
total 24
drwxr-xr-x   2 root    root    4096 Jun  6  2013 .
drwxr-xr-x 160 root    root    4096 Jul 28 17:05 ..
-rw-r--r--   1 root    root     220 Apr  3  2012 .bash_logout
-rw-r--r--   1 root    root    3486 Apr  3  2012 .bashrc
-rw-r--r--   1 root    root     675 Apr  3  2012 .profile
-rw-r-----   1 bandit1 bandit0   33 Jun  6  2013 readme
```

從本關卡的目標說明，我們知道下一關的密碼存放於 readme 檔案中， 我們可以使用本關卡建議的 cat 指令來讀取其內容。

```
bandit0@melinda:~$ cat readme
boJ9jbbUNNfktd78OOpsqOltutMc3MY1
```

Go Next!

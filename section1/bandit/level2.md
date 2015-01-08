Bandit Level 1 → Level 2
========================

### <font color="grey">Level Goal</font>

The password for the next level is stored in a file called - located in the home directory

### <font color="grey">Commands you may need to solve this level</font>

ls, cd, cat, file, du, find

### <font color="grey">Helpful Reading Material</font>

> [Google Search for “dashed filename”](https://www.google.com/search?q=dashed+filename) <br />
> [Advanced Bash-scripting Guide - Chapter 3 - Special Characters](http://tldp.org/LDP/abs/html/special-chars.html)

### Solution

    Account: bandit1
    Password: boJ9jbbUNNfktd78OOpsqOltutMc3MY1
    Host: bandit.labs.overthewire.org

使用上述帳號密碼透過 SSH 登入第一關。

```
$ ssh bandit1@bandit.labs.overthewire.org -p 22
...
bandit1@bandit.labs.overthewire.org's password:
boJ9jbbUNNfktd78OOpsqOltutMc3MY1
...
```

檢查一下家目錄的檔案列表，確實存在名為 - (dash)的檔案。

list all files

```
bandit1@melinda:~$ ls -al
total 24
-rw-r-----   1 bandit2 bandit1   33 Jun  6  2013 -
drwxr-xr-x   2 root    root    4096 Jun  6  2013 .
drwxr-xr-x 160 root    root    4096 Jul 28 17:05 ..
-rw-r--r--   1 root    root     220 Apr  3  2012 .bash_logout
-rw-r--r--   1 root    root    3486 Apr  3  2012 .bashrc
-rw-r--r--   1 root    root     675 Apr  3  2012 .profile
```

我們一樣使用 cat 指令來讀取 - (dash)檔案，但不同的是我們在檔名前加上代表當前目錄的 ”./” ( dot slash )， 以避免特殊字元的影響。

印出可疑的檔案 "-"

```
bandit1@melinda:~$ cat ./-
CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9
```

前進下一關！

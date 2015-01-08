Bandit Level 2 → Level 3
========================

### <font color="grey">Level Goal</font>

The password for the next level is stored in a file called **spaces in this filename** located in the home directory

### <font color="grey">Commands you may need to solve this level<font>

ls, cd, cat, file, du, find

### <font color="grey">Helpful Reading Material</font>

> [Google Search for “spaces in filename”](https://www.google.com/search?q=spaces+in+filename)

### Solution

   Account:bandit3
   Password:UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
   Host     :bandit.labs.overthewire.org    

使用上述帳號密碼透過 SSH 登入第三關。

```
$ ssh bandit3@bandit.labs.overthewire.org -p 22
...
bandit3@bandit.labs.overthewire.org's password:
UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
...
```

檢查家目錄檔案列表，存在一個名為 inhere 的目錄。

```
bandit3@melinda:~$ ls -al
total 24
drwxr-xr-x   3 root root 4096 Jun  6  2013 .
drwxr-xr-x 160 root root 4096 Jul 28 17:05 ..
-rw-r--r--   1 root root  220 Apr  3  2012 .bash_logout
-rw-r--r--   1 root root 3486 Apr  3  2012 .bashrc
-rw-r--r--   1 root root  675 Apr  3  2012 .profile
drwxr-xr-x   2 root root 4096 Jun  6  2013 inhere
```

使用 ls 指令檢查 inhere 目錄， 發現一個檔名前墜(prefix)為 ”.” (dot)的隱藏檔(Hidden file and hidden directory) .hidden 。

```
bandit3@melinda:~$ ls -al inhere/
total 12
drwxr-xr-x 2 root    root    4096 Jun  6  2013 .
drwxr-xr-x 3 root    root    4096 Jun  6  2013 ..
-rw-r----- 1 bandit4 bandit3   33 Jun  6  2013 .hidden
```

我們一樣使用 cat 指令來印出檔案內容。

```
bandit3@melinda:~$ cat ./inhere/.hidden
pIwrPrtPN36QITSp3EQaw936yaFoFgAB
```

前進下一關！

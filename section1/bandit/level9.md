Bandit Level 9 → Level 10
=========================

### <font color="grey">Level Goal</font>

The password for the next level is stored in the file **data.txt** among of few lines of human-readable strings starting with ‘=’ characters.

### <font color="grey">Commands you may need to solve this level</font>

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

### Solution

Account: bandit9

Password: UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR

Host: bandit.labs.overthewire.org

使用上述帳號密碼透過 SSH 登入第九關。

```
$ ssh bandit9@bandit.labs.overthewire.org -p 22
...
bandit9@bandit.labs.overthewire.org's password:
UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR
...
```

檢查家目錄，確認存在 data.txt 檔案。

```
bandit9@melinda:~$ ls -al
total 40
drwxr-xr-x   2 root     root     4096 Jun  6  2013 .
drwxr-xr-x 160 root     root     4096 Jul 28 17:05 ..
-rw-r--r--   1 root     root      220 Apr  3  2012 .bash_logout
-rw-r--r--   1 root     root     3486 Apr  3  2012 .bashrc
-rw-r--r--   1 root     root      675 Apr  3  2012 .profile
-rw-r-----   1 bandit10 bandit9 19379 Jun  6  2013 data.txt
```

這次我們使用 strings 指令印出可讀的 ASCII 文字，再透過 pipes 結合 grep 指令來協助我們尋找 = 開頭的密碼。如此一來，我們即可得到下一關的密碼。

```
bandit9@melinda:~$ strings data.txt | grep "="
Rj=G
========== the
=qy9g
,========== passwordc
========== is
=9-5
O=p~
#r=t!
7e}=eG
========== truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk
uXI/{I=VPO=
6'Q|_=Vt
:={!
yd=6
```

前進下一關！

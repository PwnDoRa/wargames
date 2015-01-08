Bandit Level 4 → Level 5
========================

### <font color="grey">Level Goal</font>

The password for the next level is stored in the only human-readable file in the **inhere** directory. Tip: if your terminal is messed up, try the “reset” command.

### <font color="grey">Commands you may need to solve this level</font>

ls, cd, cat, file, du, find


Solution
========

	Account: bandit5
	Password: koReBOKuIDDepwhWk7jZC0RTdopnAYKh
	Host: bandit.labs.overthewire.org

使用上述帳密資訊登入bandit5。
```
	bandit5@melinda:~$ ls -la
	total 24
	drwxr-xr-x   3 root root    4096 Nov 14 10:32 .
	drwxr-xr-x 167 root root    4096 Jan  2 17:30 ..
	-rw-r--r--   1 root root     220 Apr  9  2014 .bash_logout
	-rw-r--r--   1 root root    3637 Apr  9  2014 .bashrc
	-rw-r--r--   1 root root     675 Apr  9  2014 .profile
	drwxr-x---  22 root bandit5 4096 Nov 14 10:32 inhere
```
看到一個`inhere`的資料夾，切換進去檢視一下：
```
	bandit5@melinda:~$ cd inhere/
	bandit5@melinda:~/inhere$ ls -l
	total 80
	drwxr-x--- 2 root bandit5 4096 Nov 14 10:32 maybehere00
	drwxr-x--- 2 root bandit5 4096 Nov 14 10:32 maybehere01
	drwxr-x--- 2 root bandit5 4096 Nov 14 10:32 maybehere02
	drwxr-x--- 2 root bandit5 4096 Nov 14 10:32 maybehere03
	drwxr-x--- 2 root bandit5 4096 Nov 14 10:32 maybehere04
	drwxr-x--- 2 root bandit5 4096 Nov 14 10:32 maybehere05
	drwxr-x--- 2 root bandit5 4096 Nov 14 10:32 maybehere06
	drwxr-x--- 2 root bandit5 4096 Nov 14 10:32 maybehere07
	drwxr-x--- 2 root bandit5 4096 Nov 14 10:32 maybehere08
	drwxr-x--- 2 root bandit5 4096 Nov 14 10:32 maybehere09
	drwxr-x--- 2 root bandit5 4096 Nov 14 10:32 maybehere10
	drwxr-x--- 2 root bandit5 4096 Nov 14 10:32 maybehere11
	drwxr-x--- 2 root bandit5 4096 Nov 14 10:32 maybehere12
	drwxr-x--- 2 root bandit5 4096 Nov 14 10:32 maybehere13
	drwxr-x--- 2 root bandit5 4096 Nov 14 10:32 maybehere14
	drwxr-x--- 2 root bandit5 4096 Nov 14 10:32 maybehere15
	drwxr-x--- 2 root bandit5 4096 Nov 14 10:32 maybehere16
	drwxr-x--- 2 root bandit5 4096 Nov 14 10:32 maybehere17
	drwxr-x--- 2 root bandit5 4096 Nov 14 10:32 maybehere18
	drwxr-x--- 2 root bandit5 4096 Nov 14 10:32 maybehere19
```
又看到一大堆`maybehere`的資料夾，這時候我們看一下題目的說明，`The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties: - human-readable - 1033 bytes in size - not executable`，檔案是`human-readable`，大小在1033bytes，非可執行檔。

我們使用`find`指令來做多重條件的搜尋，

1. human-readable: -readable
2. 1033bytes: -size 1033c
3. not executable: ! -executable

```
	bandit5@melinda:~/inhere$ find  ./ -readable -size 1033c ! -executable -exec cat '{}' \;
	DXjZPULLxYr17uwoI01bNLQbtFemEgo7
	                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        bandit5@melinda:~/inhere$
```

以上指令下好之後就可以看到下一關的密碼了！

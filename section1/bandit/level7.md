Bandit Level 6 → Level 7
========================

### <font color="grey">Level Goal</font>

The password for the next level is stored **somewhere on the server** and has all of the following properties: - owned by user bandit7 - owned by group bandit6 - 33 bytes in size

### <font color="grey">Commands you may need to solve this level</font>

ls, cd, cat, file, du, find, grep

### Solution

Account:        bandit6

Password:       DXjZPULLxYr17uwoI01bNLQbtFemEgo7

Host:   bandit.labs.overthewire.org

使用上述帳號密碼透過 SSH 登入第六關。

```
$ ssh bandit6@bandit.labs.overthewire.org -p 22
...
bandit6@bandit.labs.overthewire.org's password:
DXjZPULLxYr17uwoI01bNLQbtFemEgo7
...
```

題目說明此關的密碼儲存於具有下列條件的檔案內。


1.	owned by user bandit7 (-user bandit7).
2.	owned by group bandit6 (-group bandit6).
3.	33 bytes in size (-size 33c).


我們一樣使用 file 指令來尋找目標。不過由於尋找整個檔案目錄會出現一堆 “Permission denied” 的錯誤訊息，因此我們在指令後附上 2>/dev/null 來執行指令，將錯誤訊息導到 /dev/null 。

```
$ find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
/var/lib/dpkg/info/bandit7.password
```
找到目標後，我們使用 cat 指令印出檔案內的密碼。

```
$ cat /var/lib/dpkg/info/bandit7.password
HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs
```

前進下一關！

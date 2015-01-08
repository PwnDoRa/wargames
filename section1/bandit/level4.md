Bandit Level 3 → Level 4
========================

### <font color="grey">Level Goal</font>

The password for the next level is stored in a hidden file in the **inhere** directory.

### <font color="grey">Commands you may need to solve this level</font>

ls, cd, cat, file, du, find

### <font color="grey">Solution

```
bandit4@melinda:~$ cd inhere/
bandit4@melinda:~/inhere$ file ./*
./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: data
bandit4@melinda:~/inhere$ cat ./-file07
koReBOKuIDDepwhWk7jZC0RTdopnAYKh
```

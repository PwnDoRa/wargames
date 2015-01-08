Bandit Level 5 → Level 6
========================

### Level

* Account:    bandit5

* Password:   koReBOKuIDDepwhWk7jZC0RTdopnAYKh

* Host:       bandit.labs.overthewire.org

### Level Goal

The password for the next level is stored in a file somewhere under the **inhere** directory and has all of the following properties:

- human-readable
- 1033 bytes in size
- not executable

### Commands you may need to solve this level

ls, cd, cat, file, du, find

### Solution

```
find ./inhere/ -readable -size 1033c ! -executable
```

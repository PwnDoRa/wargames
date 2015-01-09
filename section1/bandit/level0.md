Bandit Level 0
==============

### <font color="grey">Level Goal</font> ###

The goal of this level is for you to log into the game using SSH. The host to which you need to connect is **bandit.labs.overthewire.org**. The username is **bandit0** and the password is **bandit0**. Once logged in, go to the [Level 1](level1.md) page to find out how to beat Level 1.

### <font color="grey">Commands you may need to solve this level</font> ###

ssh

### <font color="grey">Helpful Reading Material</font> ###

> [Secure Shell (SSH) on Wikipedia](http://en.wikipedia.org/wiki/Secure_Shell) <br />
> [How to use SSH on wikiHow](http://www.wikihow.com/Use-SSH)

### Solution ###

> Account: bandit0 <br />
> Password: bandit0 <br />
> Host: bandit.labs.overthewire.org

本關卡旨在引導與告知使用者透過 SSH 連上伺服器，只要使用上述帳號密碼登入第零關後即可開始。Let’s fight!

```
$ ssh bandit0@bandit.labs.overthewire.org -p 22
...
bandit0@bandit.labs.overthewire.org's password:
bandit0
...
```


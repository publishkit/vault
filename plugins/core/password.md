---
alias: $password
title: Password
description: password protect a page
---
# password

The password plugin is technically not a plugin. You specify a password at the root of the frontmatter, and the content get sha256 encoded with the password. Of course the password is removed from the export and never enters the kit.

## use

```yml
password: foobar
```

## options

Password can be applied: 
- globaly - in the `kitrc.md`
- on a directory basis - in a `dirrc.md` file in that directory
- on a file basis

It's a single password by file.

## demo

Try accessing this [[demo/password|demo]] page using `foobar` as the password.
---
alias: $password
description: Restrict access to your site
tags: [plugin, core, password]
---
# password

> Restrict access to your site, directories or pages.
 


## use

Restrict access by adding a password at the root of the frontmatter:
- site level - in the [[doc/services/kitrc|kitrc]]
- directory level - in the [[demo/dirrc]] file in that directory
- file level

```yml
password: foobar
```

- Only 1 password by file is supported.
- Content is sha256 encoded.

## demo

Try accessing this [[demo/password|demo]] page using `foobar` as the password.
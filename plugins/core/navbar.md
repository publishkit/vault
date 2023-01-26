---
core: true
author: louis
description: Add a navigation menu
---
# navbar

> Add a navigation menu to your site

## use

```yaml
plugins:
  navbar: true
```

- Create a `navbar.md` file at the root of your `vault`.
- Add your navigation links, and export the file.
- A file called `navbar.json` will be created at the root of your `kit` folder.

## basic

To add a basic navigation, simply add a list of links.

```markdown
- [Link1](relative/path/to/link1)
- [[wikilink|Link2]]
- [Link3](http://external.link.com)
```

![[plugin-navbar-s1.png]]

## icons

You can customize the icons by adding 2 pipes `||` after your link, followed by one the 1664 icons name from [boxicons.com](https://boxicons.com/):

```markdown
- [Link1](relative/path/to/link1) || bx-paper-plane
- [[wikilink|Link2]] || bx-cog
- [Link3](http://external.link.com)
```

![[plugin-navbar-s2.png]]

## nested

You can opt for a nested navigation menu by nesting links lists into sections.

```markdown
- section 1
  - [Link1](relative/path/to/link1)
  - [[wikilink|Link2]]
  - [Link3](http://external.link.com)
- section 2
  - [Link4](relative/path/to/link4)
- foobar
  - [Link5](relative/path/to/link5)
```

![[plugin-navbar-s3.png]]

To make a section closed by default, just add a checked checkbox `[x]` in front of your section name.

```markdown
- [x] section 2
  - [Link4](relative/path/to/link4)
```

![[plugin-navbar-s4.png]]
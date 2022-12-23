---
title: PublishKit
alias: [publishkit, home]
tags: home, rocknroll
---
# PublishKit

> Turn your notes into a website

`= this.title` is an Obsidian plugin that let you export your notes into `html` files ready to be served. 



## features

- [x] single config file (`pkrc`)
- [x] `[[wiki links]]`
- [x] dataview support
- [x] full-text search
- [ ] attachements search
- [x] custom table of content
- [x] assets support (images & pdfs)
- [x] dark mode
- [x] seo friendly (open graph)
- [x] callouts / admonitions
- [x] bootstrap utilities
- [ ] navigate between your site & obsidian
- [ ] embed pages
- [ ] password protected pages
- [ ] tags

## install

In Obsidian settings, go to community plugins, search & install "**`=this.title`**".

## use

Now, whenever you want to export a file, you can either:
- click the paper-airplane icon <i class='bx bx-paper-plane'></i> in the left bar
- open command palette with <kbd>⌘</kbd>+<kbd>⇧</kbd>+<kbd>P</kbd> and run `PublishKit: export file`
- or assign a shortcut to that command in the Obsidian settings

> [!info]
> Each note is exported independently. When you make a modification to a note you have to export the note again.


## configuration

When you export a note for the first time, `= this.title` will ask you to specify the folder where you want your notes to be exported.

It will then create a regular markdown file called `pkrc` at the root of your vault. This file holds the global configuration of your `= this.title` website. You can find the list of settings [[settings|here]].

Like any other file, you have to export your `pkrc` file for `= this.title` to work.


## assets

`=this.title` takes care of exporting assets (images and pdfs) related to your note. Assets are exported in the `site_assets` folder specified in your `pkrc` config file.

> [!info]
> The assets folder is relative to the publish kit export `pk_folder`. 
> By default it's `/assets`.

The export structure will match exactly with your vault structure, so you get Folders support.




---

## limitations
- desktop only (use nodejs for filesystem)
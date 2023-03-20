---
title: Obsidian Plugin
alias: $setup.obsidian
---
# Obsidian

- the plugin is desktop only (uses node filesystem)
- it has only been tested on mac
- more at https://publishkit.dev

## install

- repo url https://github.com/publishkit/obsidian
- manually clone the repo inside your `.obsidian/plugins` folder.
- or install via the [BRAT](https://github.com/TfTHacker/obsidian42-brat) plugin

<!-- In Obsidian settings, go to community plugins, search & install KIT". -->

## use

- click the paper-airplane icon <i class='bx bx-paper-plane'></i> in the left bar
- or in command palette, run `KIT: export file` or `KIT: export vault`
- you can assign a shortcut to any of those commands. <kbd>⌘</kbd>+<kbd>⇧</kbd>+<kbd>E</kbd> works pretty well for single file export.

> [!note] Vault export
> Make sure you configure the `include` & `exclude` vault parameters inside the `kitrc`.


## configuration

When you export a note for the first time, `= this.title` will ask you to specify the `kit` folder (the folder where you want your notes to be exported). You have to provide an absolute url to the folder.

It will create a `kitrc.md` at the root of your vault, containing the global configuration of your kit. Learn about the [[doc/services/kitrc|kitrc]] file.

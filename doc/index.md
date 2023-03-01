---
title: User Guide 📘
alias: User Guide
---
# User Guide 📘

The Kit philosophy is to be able to publish markdown content on the web, effortlessly. The kit offers a set of tools designed around powerful heuristics that offers a range between zero configuration to advanced cross content workflows.

Each markdown file that the kit exports is processed and converted into a static HTML file, saved in the `kit` folder you configured.

Once a file, or files from a directory/vault, are exported, you can publish/deploy the `kit` folder to any hosting provider. The Kit, as its name implies, is just a kit, and doesn't provide hosting.

The kit embraces the `static` experience and is meant to be deployed at the edge of CDN's. They offer ultra-high speed delivery of your content to the users, worldwide, for free. One other advantage about static apps is because all pages are delivered at nearly instant speed, they make for very consistent and pleasant browsing experiences. Which is something we are deeply focusing on. Our goal is to design first class publishing experiences for content first applications.

## usage

- via the [[cli|CLI]]
- via our PKM plugin 
- or both

Using the PKM plugin over the CLI has the advantage of benefiting from the PKM internal features. For example, [[Obsidian]] users can use the wonderful `dataview` plugin to build out their content, and the queries will get published nicely.

Unlike the CLI who parses and exports the markdown into HTML, the PKM integration bypass the markdown processing, and only processes the PKM HTML render, allowing PKM plugins transformations to be publishable. Yes my friend!

*Currently, only [[Obsidian]] is supported. More pkm's on the way.*


## exporting

```bash
# single file
kit export index.md

# multiple files
kit export kitrc.md blog/myarticle.md
```

In the kit folder, the converted files, alongside linked assets like images & PDFs, will mirror the same folder structure as their respective source file. Exported, the file `blog/myarticle.md` in your vault folder, will be located at  `blog/myarticle.html` in the kit folder.

> [!tip] html files
> They are regular html. They contain a header, a script pointing to the kit source, and the actual html content. The content is wrapped in a `<template id="content" />` tag, and is only made visible after the page has loaded and the plugins have all registred.



## kit preview

Before deploying your changes to your hosting provider, you can live preview your kit application locally. Assuming you have nodejs installed on your machine, open your terminal, navigate to your kit folder and serve the folder by running:

```bash
cd /path/to/kit
npx http-server
```

> [!tip] CLI command
>  You can run `kit serve`command, it's a proxy to the node http-server module, but can automatically open the browser. To specify a port run `pk serve -p 1337`

## publishing

The `kit` can be hosted anywhere. 
Preferably on ultra-fast CDN's :) 
This website is hosted on GitHub pages .


![[doc/setup/index|Setup]]

![[doc/services/index|Services]]

![[top level variables]]
---
title: PublishKit Cli
alias: $setup.cli
---
# Cli setup

The Cli


## install

```bash
npm -g install @publishkit/cli
// or
yarn -g add @publishkit/cli
```


## export

```bash
# single file
kit export index.md

# multiple files
kit export kitrc.md blog/myarticle.md
```

## serve

Serve your kit folder locally in the browser. In your kit folder run:

```bash
kit serve -p 1337
```

> [!tip] 
>  The serve command is an alias of the node [http-server](https://github.com/http-party/http-server) module, but can automatically open up the browser. To specify a port run `pk serve -p 1337`


## ls

The `ls` command is pretty handy and let you list all the files that match the `include` & `exclude` settings in your [[doc/services/kitrc|kitrc]]. Make sure you are in your `vault` folder (the folder containing your markdown files) and run:

```bash
kit ls
```
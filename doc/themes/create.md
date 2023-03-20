---
title: Create a theme
alias: Create a theme
---
# Create a theme

Creating a theme is very easy. In a javascript file, return a class defining your theme, and start tweaking.

The exemple below is the actual `@default` theme of the kit. You can look at the source file [here](https://github.com/publishkit/community/blob/main/themes/default.js).

```js
eturn class Theme extends BaseTheme {
  constructor(id, options) {
    super(id, options, {
      highlight: "nord",
      font: "Marcher",
    });
  }

  style = async () => {
    return this.modes.render();
  };
};
```


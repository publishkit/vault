---
title: Create a theme
alias: Create a theme
tags: [theme, create]
---
# Create a theme

Creating a theme is very easy. In a javascript file, return a class defining your theme, and start tweaking.

The exemple below is the actual `@default` theme of the kit. You can look at the source file [here](https://github.com/publishkit/community/blob/main/themes/default.js).

```js
return class Theme extends BaseTheme {
  constructor(id, options) {
    super(id, options, {
      highlight: "nord",
      font: "Marcher",
    });
  }

  style = async () => {
    const { modes } = this;
    
    modes.all(`
      --primary: red;
      
      div {
	    p {
          color: var(--primary)
        }
      }
    `)
    
    return modes.render();
  };
};
```


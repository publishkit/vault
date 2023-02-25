---
title: Create a plugin
alias: $plugins.create
---
# Create a plugin

Creating a plugin is very easy. In a javascript file, return a class defining your plugin.

```js
return class Plugin extends BasePlugin {
  constructor(id, options) {
    super(id, options);

	// default options
    this.options = {
      fontsize: 10,
      rate: 35,
      ...this.options,
    };
  }

  render = async () => {
    // register ui
  };
  
  bind = async () => {
    // bind ui
  };
};
```

## lifecycle

When a plugin is registered, it goes through a simple lifecycle.

```
init -> render -> bind
```


### init

Some plugins may require some initialisation before they get rendered. In that case just provide an `init` function to your plugin class.

> [!info]
> - If you don't provide an `init` function, the lifecycle will continue as normal.
> - If your `init` function returns `false`, then the lifecycle will stop and the plugin won't be registered.

```js
init = async () => {
	// do stuff
	// if everything ok, return true
	// else return false
	return true
}
```


### render

The `render` method is where you can register UI components.

```js
render = async () => {
	// do stuff
}
```


### bind

The `bind` method is where you bind your UI components.

```js
bind = async () => {
	// do stuff
}
```


## UI

More on `UI` later !

### addAction

### addElement

### addHeaderIcon

### addModal


## style

The `style` function is where you style your components. You can write vanilla css, or [lesscss](https://lesscss.org/).

```js
style = async () => `
  [id="right.toc.main"] {
    ul {
      padding: 0;
      margin: 0;

      li {
        list-style: none;
        &:hover {
          background: red;
        }
      }
    }
  }
 
  @media (max-width: 576px) {
    [id="right.toc.main"] {
      display: none;
    }
  }
`;
```
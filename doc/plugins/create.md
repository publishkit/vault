---
title: Create a plugin
alias: Create a plugin
tags: [plugin, create]
---
# Create a plugin

Creating a plugin is very easy. In a javascript file, return a class defining your plugin, and set some default options if needed.

```js
return class Plugin extends BasePlugin {
  constructor(id, options) {
    super(id, options, {
      fontsize: 10,
      color: "purple",
    });
  }

  render = async () => {
    // create some ui
  };
  
  bind = async () => {
    // bind ui
  };
};
```

## lifecycle

When a plugin is registered, it goes through the following optionnal life cycles, each of them giving you an opportunity to define your plugin.

```js
await plugins.init();
await plugins.deps();
await plugins.style();
await plugins.render();
await plugins.transform();
await plugins.bind();
```


### init

Some plugins may require some initialisation before they get rendered. In that case, just provide an `init` method to your plugin class.

> [!info]
> - If you don't provide an `init` function, the lifecycle will continue as normal.
> - If your `init` function returns `false`, then the lifecycle will stop and the plugin won't be registered.

```js
init = async () => {
	// do stuff, load config
	// if everything ok, return true
	// else return false
	return true
}
```


### deps

The `deps` method let you include external dependencies, like `js` et `css` files. The method can be a flat array, or a function, if you need access to props.

```js
deps: [
	"https://cdn.jsdelivr.net/lib.js",
	"https://cdn.jsdelivr.net/theme-v2.css"
]

// or dynamically

deps: async () => [
	"https://url.com/lib.js",
	`https://url.com/theme-v${this.options.version}.css`
]
```

It's also possible to push a depedency inside the constructor:

```js
constructor(id: string, options) {
	super(id, options);
	this.deps.push("https://url.com/lib.js");
}
```

### style

The `style` function is where you style your components. You can write vanilla css, or [lesscss](https://lesscss.org/).

```js
style = async () => `
  [id="toc.list"] {
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
    [id="toc.list"] {
      display: none;
    }
  }

  /* conditional render */
  ${this.options.color == "red" ? `
    [id="toc.list"] {
      ul {
        background: ${this.options.color};
      }
    }
  ` : ""}
`;
```

### render

The `render` method is where you can register UI components.

```js
render = async () => {
	const { ui, options } = this;
    
    const cta = `<i class="bx bx-dollar"></i>`
	const modal = `
	  <input type="text" value="${options.amount}" />
	  <button data-click="$stripe.pay()">
	    Pay Order
	  </button>
	`;
	
	ui.addModal("my-modal", modal);
	ui.addElement("my-cta", "header.right", cta);
}
```

### transform

This is where it's appropriate to do all kind of dom manipulation. All plugins have rendered, but can still be transformed.

```js
transform = async () => {
	const { $dom, $utils } = window;
    const headings = $dom.body.find("h1, h2, h3");

    headings.each(function () {
      const slug = $utils.s.slugify($(this).text());
      this.id = "heading-" + slug;
    });
}
```

### bind

The `bind` method is the last cycle, and is where you bind your UI components and make them dynamic.

```js
bind = async () => {
	const { ui } = this;
    
    const cta = ui.get("my-cta")
    const modal = ui.get("my-modal")
	
	cta.el.on("click", function(){
	  modal.open()
	})
}
```


## UI

More on building `UI` later !

### addAction

### addElement

### addHeaderIcon

### addModal



---
title: Plugins
alias: plugins
---

# Plugins

PublishKit is highly extendable via plugins.

## core

```dataview
list 
from "plugins"
where file.link != [[plugins/index]]
sort file.name
```

## create a plugin

```js
return (async (plugin, app) => {
    
    plugin.code = async (options, app) => {
        // do stuff
    }

    return plugin

})({ id: 'unique-plugin-id' }, window.App)
```

## lifecycle

```js
plugin.init = async (options, app) => {
	// do stuff
	// if everything ok, return true
	// else return false
	return true
}
```

---
alias: $chargebee
core: true
author: louis
description: Chargebee payment platform
tags: [plugin, community, chargebee]
---
# chargebee

> Chargebee payment platform

## use

```yaml
plugins:
  chargebee: true
```

## options

```yaml
chargebee:
  id: xxx
```

### portal

```markdown
<button data-click="$chargebee.portal.open()">
  Open Portal
</button>
```

### add plan

```markdown
<button 
	data-cb-type="checkout" 
	data-cb-item-0="perso-yearly"
>
  Buy
</button>
```
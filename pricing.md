---
title: Pricing
plugins:
  toc: false
  chargebee: "@chargebee|site:studio1337"
props:
  period: monthly
  price: "(plan, period) => ~(`plans.${plan}.${period}`)"
  plans: 
    free:
      monthly: 0
      yearly: 0
    perso:
      monthly: 5
      yearly: 50
    pro:
      monthly: 50
      yearly: 500
---

<!-- switch --><p data-switch data-bind="~period" class="mb-5 mx-auto"></p>
- monthly
	- label: <i class="bx bx-calendar me-2"></i>monthly
- yearly
	- label: yearly  <i class="bx bxs-gift ms-2" ></i>

<!-- end:switch --><p data-end></p>

<!-- cards --><p data-card class="grid-auto" data-item-class="text-center"></p>
- ## free 
	- <i class="bx bx-infinite"></i> lifetime offer
	- ---
	- for [OSS](https://en.wikipedia.org/wiki/Open-source_software) projects
	- & local kits
	- ---
	- <a data-tooltip="discord"><i class="bx bxl-discord"></i></a> support
	- <button class="outline mt-4" data-cb-type="checkout" data-cb-item-0="free-yearly"><i class="bx bxs-plus-circle me-2"></i>add Kit</button>
- ## perso
	- <i class="bx bx-target-lock"></i> *blogs, digital gardens, projects...*
	- ---
	- <span class="fs-5">~price("perso", ~period) + "€"</span>
	- *<small>~period</small>*
	- ---
	- <a data-tooltip="email"><i class="bx bx-mail-send"></i></a> + <a data-tooltip="discord"><i class="bx bxl-discord"></i></a> support
	- <button class="primary mt-4" data-show="~period=='monthly'" data-cb-type="checkout" data-cb-item-0="perso-monthly"><i class="bx bxs-plus-circle me-2"></i>add Kit</button><button class="primary mt-4" data-show="~period=='yearly'" data-cb-type="checkout" data-cb-item-0="perso-yearly"><i class="bx bxs-plus-circle me-2"></i>add Kit</button>
- ## pro
	- <i class="bx bx-target-lock"></i> *anything business related*
	- ---
	- <span class="fs-5">~price("pro", ~period) + "€"</span> 
	- *<small>~period</small>*
	- ---
	- <i class="bx bx-alarm"></i> priotity support
	- <button class="primary mt-4" data-show="~period=='monthly'" data-cb-type="checkout" data-cb-item-0="pro-monthly"><i class="bx bxs-plus-circle me-2"></i>add Kit</button><button class="primary mt-4" data-show="~period=='yearly'" data-cb-type="checkout" data-cb-item-0="pro-yearly"><i class="bx bxs-plus-circle me-2"></i>add Kit</button>

<!-- end:cards --><p data-end></p>


<!-- div --><p data-div class="m-auto" style="max-width:600px;"></p>
## about kits

- You can activate as many kits as desired.
- Each kit has a unique `id`
- Each kit is associated with a subscription. 
- Kits are managed via the <a data-click="$chargebee.portal.open()"><i class="bx bxs-cog me-2"></i>Kit Portal</a>
- The only configuration is a `domain` URL.

> [!tip] kit portal
> - simply send the OneTimePassword received by email and you will be logged into the portal, to manage your kits and billing details.
> - the portal is provided by our payment provider [chargebee](https://www.chargebee.com/).
> - untill you decide to publish your kit, you can leave "localhost" as `domain` url.



## invoicing

Our payment provider, [chargebee](https://www.chargebee.com/), simplifies subscriptions based payments on top of a [stripe](https://stripe.com) or PayPal account. 

From the <a data-click="$chargebee.portal.open()"><i class="bx bxs-cog me-2"></i>Kit Portal</a> you can manage all of your subscriptions (kits) and download associated invoices.

We are a French based company, and for now, only charge in euros, vat included.


## free usage

Kits are 100% free to use and register for:
- any open source content
- anyone using the kit locally on their machine. 

As soon as it leaves your local environment, the kit will require a kit `id` to activate. The kit id has to be specified in the `site.id` config of the [[doc/services/kitrc|kitrc]]:

```yaml
site:
  id: "my-kit-id"
```

> [!note] localhost 
> a kit can be used locally without having to be registered. use the cli `kit serve` command and to open your kit folder in the browser on localhost.


<!-- end:div --><p data-end></p>

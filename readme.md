<h1 align="center">eleventy-plugin-ebay-sync</h1>

<h4 align="center">An Eleventy <a href="https://www.11ty.dev/docs/plugins/">plugin</a> to sync products from your 11ty store to your eBay store.</h4>

<p align="center">
    <a href="https://twitter.com/intent/tweet?text=eleventy-plugin-ebay-sync%20%7C%20An%20Eleventy%20plugin%20to%20sync%20products%20from%20your%2011ty%20store%20to%20your%20eBay%20store.&url=https://www.npmjs.com/package/eleventy-plugin-ebay-sync&hashtags=eleventy,eleventy-plugin,github,eBay,eleventy-store,eBay-sync"><img alt="tweet" src="https://img.shields.io/twitter/url/http/shields.io.svg?style=social" /></a>
    <a href="https://www.npmjs.com/package/eleventy-plugin-ebay-sync"><img alt="npm" src="https://img.shields.io/npm/v/eleventy-plugin-ebay-sync"></a>
</p>

## 🚀 Installation

Install from [npm](https://www.npmjs.com/package/eleventy-plugin-ebay-sync):

```bash
npm i -D eleventy-plugin-ebay-sync
```

## 😎 What does it do?

This plugin will sync products between your 11ty store and your eBay store each time your site is built.

## 🏃 Usage

Simply add a few additional properties to your product yaml front matter.

First, set some environment variables.

```bash
EBAYAPPID=<get the app id from ebay>
EBAYAPPSECRET=<get the app secret (clientId) from ebay>

# see https://developer.ebay.com/DevZone/merchandising/docs/Concepts/SiteIDToGlobalID.html
EBAYSITEID=eBayApi.SiteId.EBAY_US # default

EBAYMARKETPLACEID=eBayApi.MarketplaceId.EBAY_US # default

EBAYLANGUAGE=eBayApi.Locale.en_US # default

EBAYCONTENTLANGUAGE=eBayApi.ContentLanguage.en_US # default

EBAYSANDBOX=false # default
```

Next, import in your `.eleventy.js`:

```js
const ebaySync = require('eleventy-plugin-ebay-sync');

module.exports = function (eleventyConfig) {
  eleventyConfig.addPlugin(ebaySync);
};
```

For example, on `product_1.md`:

```yaml
---
name: Product 1
price: $10
eBayPercentIncrease: 15 # increase base price by a % for ebay (optional)
eBayFixedIncrease: 10 # increase base price by a $ for eBay (optional)
eBayId: 1
# other required attributes?
```

## ⚙️ Details

This plugin uses the [`ebay-api`](https://hendt.gitbook.io/ebay-api/) package to keep things in sync with eBay.

Check out the [samples](https://github.com/christopherpickering/eleventy-plugin-ebay-sync/tree/master/sample) site, or clone and run locally with `npm test`.

## 🦘 Out in the Wild

- [the Bible House](https://bible.house)

---
date: "2025-04-22T17:19:54+09:00"
draft: true
title: "Unit Testing Shopify Checkout Extension"
---

## About Shopify Checkout Extension

As of xx, Shopify has introduced a new way for third party apps to develop apps for checkout pages called Checkout Extension.

It allows developer to build apps in a safe sandboxed environment which ensures that apps do not have the ability to write code that could detrimentally affect the store's checkout experience.

Prior to this, the common way for third party apps to add a widget was to use Script Tags. Script Tags allows an app to load a JavaScript file onto most pages on a Shopify store, and this includes the order status page and thank you page of a Shopify store.

Using Script Tags however exposes merchants and their customers to potentially malicious code as any JavaScript could be executed when loaded via the Script Tag.

TODO: We will touch on React testing

...

The Checkout Extension being in a sandboxed environment however also makes it difficulty to write automated tests for. This is because the traditional method of writing a front end test would be to render the component to be tested in a virtual DOM.

This would not work for Checkout Extensions because the way a Checkout Extension works is by utilising a technology also developed by Shopify called [Remote DOM](https://github.com/Shopify/remote-dom). When you write a Remote DOM component, the JavaScript produced actually does not include any information about how the component should be rendered.

For example, in React if you were to render a `<button>` element in JSX, it would render the button element in HTML but this is not the case for Checkout Extension.

Who dictates what should be rendered is actually a Remote DOM host and when we write the Checkout Extension component we are writing the Remote DOM client. The Remote DOM host in this case would be on Shopify's back end which would handle translating our client side code to actual HTML element and communicating that to the web front end.

## Setting up the example project

## Writing our first test

---

About Gojiberry

---
layout: page
homepage: true
---

# Overview

<div class="alert alert-warning" markdown="1">
**Warning**: These docs are currently being worked on and are incomplete. I am doing quite a bit and writing good documentation is *hard*. Bare with me.
</div>

> Check Yo Self is  a site to check the grammar of your markdown blog posts/texts.

[![Travis](https://img.shields.io/travis/twhite96/checkyoself.svg)](https://travis-ci.org/twhite96/checkyoself)
[![Greenkeeper badge](https://badges.greenkeeper.io/twhite96/checkyoself.svg)](https://greenkeeper.io/)
[![Twitter Follow](https://img.shields.io/twitter/follow/TiffanyW_412.svg?style=social&label=Follow)](https://twitter.com/TiffanyW_412)
[![MIT Licence](https://badges.frapsoft.com/os/mit/mit.svg?v=103)](https://opensource.org/licenses/mit-license.php)
[![Open Source Love](https://badges.frapsoft.com/os/v1/open-source.svg?v=103)](https://github.com/ellerbrock/open-source-badges/)
[![GitHub commits](https://img.shields.io/github/commits-since/twhite96/checkyoself/0.0.2.svg?maxAge=2592000)](https://github.com/twhite96/checkyoself)

Frustrated by Grammarly and Hemingway apps' inability to process markdown blog posts, I decided to make my own site to process markdown blog posts or other texts. I settled on [Materialize.css](http://materializecss.com/) a [Material Design Lite](https://getmdl.io/index.html) library for the UI because I like colorful things.

# Installation

No installation needed. Just fork the repo, install dev dependencies, and get running.


## Development setup

There are a few dependencies and I want to thank [@btford](https://github.com/btford) and the [@NaturalNode](https://github.com/NaturalNode) Organization for their awesome tools which without them this wouldn't be as easy.

Fork the repo, and add your own `package.json` file with:

```bash
npm init
```
and fill in all the gritty details.

The site uses Brian Ford's `write-good` linter for native English and NaturalNode's `natural` for the tokenizers in its Node npm module.

To install `write-good`:

```bash
npm install write-good
```
...and natural:

```bash
npm install natural
```

# Usage example

You can basically do what you like with this. I am using MEN stack with Mongo, Express, and Node, using RESTful routes and hosting on Heroku. It is up to you how you want to build on top of what I have here.

## Using the `write-good` library

You need to require it in your `app.js` or whatver you're going to use to route interaction through the app (if you're using MEAN or MEN). Your script could look something like:

```javascript
var writeGood = require('write-good');

const inputs = document.getElementById('textarea').getElementsByTagName('input');
const input = [];
for (let i = 0, l = inputs.length; i < l; ++i) {
    if (inputs[i].value.length) {
        input.push(inputs[i].value);
    }
}

let suggestions = writeGood(input);

const div = document.createElement('div');
for (let i = 0, l = input.length; i < l; ++i) {
    div.innerHTML += input[i] + "<br />";
}
document.body.appendChild(div);
```

## Meta

I'm on the Twitters at  – [@TiffanyW_412](https://twitter.com/TiffanyW_412)  For feedback and bugs:
email: <feedback@tiffanyrwhite.com>

Distributed under the MIT license. See ``LICENSE`` for more information.

[https://github.com/twhite96/checkyoself](https://github.com/twhite96/checkyoself)

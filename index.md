---
layout: page
homepage: true
---

# Overview

<div class="alert alert-warning" markdown="1">
**Warning**: These docs are currently being worked on and are incomplete. I am doing quite a bit and writing good documentation is *hard*. Bear with me.
</div>

> Check Yo Self is  a site to check the grammar and spelling of your markdown blog posts/texts.

[![Travis](https://img.shields.io/travis/twhite96/checkyoself.svg)](https://travis-ci.org/twhite96/checkyoself)
[![Greenkeeper badge](https://badges.greenkeeper.io/twhite96/checkyoself.svg)](https://greenkeeper.io/)
[![Twitter Follow](https://img.shields.io/twitter/follow/TiffanyW_412.svg?style=social&label=Follow)](https://twitter.com/TiffanyW_412)
[![MIT Licence](https://badges.frapsoft.com/os/mit/mit.svg?v=103)](https://opensource.org/licenses/mit-license.php)

Frustrated by Grammarly and Hemingway apps' inability to process markdown blog posts, I decided to make my own site to process markdown blog posts or other texts. I settled on [Materialize.css](http://materializecss.com/) a [Material Design Lite](https://getmdl.io/index.html) library for the UI because I like colorful things.

# Installation

You'll need to install dev dependencies.


## Development setup

There are a few dependencies and I want to thank [@btford](https://github.com/btford) for his awesome library which without him this wouldn't be as easy.

Fork the repo, and add your own `package.json` file with:

```bash
npm init
```
and fill in all the gritty details.

The site uses Brian Ford's `write-good` linter for native English and [@danakt](https://github.com/danakt/spell-checker.js)'s `spell-checker-js` for the spellchecker I am using.

To install `write-good`:

```bash
npm install write-good
```
...and `spell-checker`:

```bash
npm install spell-checker
```

# Usage example

You can basically do what you like with this. I am using MEN stack with Mongo, Express, and Node, using RESTful routes and hosting on Heroku. It is up to you how you want to build on top of what I have here.

## Using the write-good library

You need to require it in your `app.js` or whatver you're going to use to route interaction through the app (if you're using MEAN or MEN). Your script could look something like:

```javascript
const writeGood = require('write-good');

let suggestions = writeGood('So the toilet paper was eaten by my cat');

// Will return an array of suggestions

suggestions:
[{
    suggestion: "omit 'So' from the beginning of sentences",
    index: 0, offset: 2
 }, {
     suggestion: "' was eaten' is passive voice",
     index: 20, offset: 19
 }]
```

You can also disable checks for certain properties:

```javascript
const writeGood = require('write-good');

let suggestions = writeGood('So the toilet paper was eaten by my cat', { passive: false });

// suggestions: [ ]
```

## Using the spell-checker-js library

You can easily use this `spell-checker` library in this project by requiring it and invoking it with something like:

```javascript
const spell = require('spell-checker-js')
 
// Load dictionary
spell.load('en')
 
// Check spelling
const check = spell.check('Some **text** to chec!');
 
console.log(check)

// Returns an array of spell-checked words
// ['chec']
```

# Authentication



## Meta

I'm on the Twitters at  – [@TiffanyW_412](https://twitter.com/TiffanyW_412)  

For feedback and bugs:
email: <bugs@tiffanyrwhite.com>

Distributed under the MIT license. See ``LICENSE`` for more information.

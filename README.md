[![npm (scoped)](https://img.shields.io/npm/v/wscript-avoider.svg)](https://www.npmjs.com/package/wscript-avoider) 
[![npm](https://img.shields.io/npm/dt/wscript-avoider.svg)](https://www.npmjs.com/package/wscript-avoider)
[![license](https://img.shields.io/github/license/xpack/wscript-avoider-js.svg)](https://github.com/xpack/wscript-avoider-js/blob/xpack/LICENSE) 
[![Travis](https://img.shields.io/travis/xpack/wscript-avoider-js.svg?label=linux)](https://travis-ci.org/xpack/wscript-avoider-js)

## Windows Script Host avoider

A `node.js` module to avoid running on [Windows Script Host](https://msdn.microsoft.com/en-us/library/9bbdkx3k.aspx).

The module exports a class `WscriptAvoider` with a single static function (`quitIfWscript(name)`), that checks if the global object `WScript` is defined and quits if true.

## Prerequisites

A recent `node.js` (>7.x), since the ECMAScript 6 class syntax is used.

## Easy install

This module is available as [**wscript-avoider**](https://www.npmjs.com/package/wscript-avoider) from the public repository, use `npm` to install it:

```bash
$ npm install wscript-avoider
```

The development repository is available from the GitHub [xpack/wscript-avoider-js](https://github.com/xpack/wscript-avoider-js) project.

## How to use

The module has only one function; call it with the application name as argument and normally it should return. If bad luck struck and **Windows Script Host** grabbed the script, a message is displayed and the application abruptly terminates.

```javascript
const appName = 'name'
// Equivalent of import { WscriptAvoider } from 'wscript-avoider'
const WscriptAvoider = require('wscript-avoider').WscriptAvoider
WscriptAvoider.quitIfWscript(appName)
```

The string `name` should be the name of the current node.js application, as launched from a terminal window (for example `xcdl`).


<p align="center">
  <a href="https://travis-ci.org/ccckmit/mdo"><img src="https://img.shields.io/travis/ccckmit/mdo.svg" alt="Travis"></a>
  <a href="http://standardjs.com"><img src="https://img.shields.io/badge/code_style-standard-brightgreen.svg" alt="Standard - JavaScript Style Guide"></a>
  <a href="https://www.npmjs.com/package/mdo"><img src="https://img.shields.io/npm/dm/mdo.svg" alt="npm downloads"></a>
  <a href="https://www.npmjs.com/package/mdo"><img src="https://img.shields.io/npm/v/mdo.svg" alt="npm version"></a>
</p>

# mdo -- Markdown Object (Parser)

## Install

```
$ npm install mdo
```

## Example

File: mdoTest.js

```
var fs = require("fs");
var M  = require("mdo");

var text  = fs.readFileSync("test.mdo", "utf8")
var obj = M.parseMdo(text);
console.log("json=%s", JSON.stringify(obj, null, 2));
```

Input: test.mdo

```
title: Markdown Object Parser
author: { id:"ccc",
  name: "Chung-Chen Chen",
  email: "ccckmit@gmail.com"
}
keywords: [ "Markdown", "Parser", "JSON", "Object", "markup"]
publish: 2017/01/10
version: 1.01

used_by: 
package  | description
---------|-------------------
bookdown | A book publishing system for markdown
rlab     | A scientific library like R+Matlab in JavaScript
```

## Run 

```
$ node mdoTest.js
json={
  "title": "Markdown Object Parser",
  "author": {
    "id": "ccc",
    "name": "Chung-Chen Chen",
    "email": "ccckmit@gmail.com"
  },
  "keywords": [
    "Markdown",
    "Parser",
    "JSON",
    "Object",
    "markup"
  ],
  "publish": "2017/01/10",
  "version": 1.01,
  "used_by": [
    {
      "package": "bookdown",
      "description": "A book publishing system for markdown"
    },
    {
      "package": "rlab",
      "description": "A scientific library like R+Matlab in JavaScript"
    }
  ]
}
```





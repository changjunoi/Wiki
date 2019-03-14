# remark-copywriting-correct

[![version](https://img.shields.io/npm/v/remark-copywriting-correct.svg?style=flat-square)](http://npm.im/remark-copywriting-correct)
[![MIT License](https://img.shields.io/npm/l/remark-copywriting-correct.svg?style=flat-square)](http://opensource.org/licenses/MIT)

给 Markdown 中英文自动插入空格的 [remark](https://github.com/wooorm/remark) 插件（使用 [https://github.com/rikakomoe/copywriting-correct](https://github.com/rikakomoe/copywriting-correct)）。

## Install

```bash
npm install remark-copywriting-correct
npm install remark-math-space
# remark-math-space 用来在行内公式两侧加空格
```

## Usage

```js
"use strict";
var remark = require("remark");
var parse = require("remark-parse");
var math = require("remark-math");
var ww = require("remark-copywriting-correct");
var sp = require("remark-math-space");

var fs = require("fs");
var www = fs.readFileSync("a.md");

const doc = "中文abc中文$a_i$中文";
remark()
  .use(parse)
  .use(math)
  .use(ww)
  .use(sp)
  .process(doc, function(err, res) {
    console.log(String(res));
  });
// => 中文 abc 中文 $a_i$ 中文
```

## LICENSE

[MIT](./LICENSE)

![Async Logo](https://raw.githubusercontent.com/caolan/async/master/logo/async-logo_readme.jpg)

[![Build Status via Travis CI](https://travis-ci.org/caolan/async.svg?branch=master)](https://travis-ci.org/caolan/async)
[![Build Status via Azure Pipelines](https://dev.azure.com/caolanmcmahon/async/_apis/build/status/caolan.async?branchName=master)](https://dev.azure.com/caolanmcmahon/async/_build/latest?definitionId=1&branchName=master)
[![NPM version](https://img.shields.io/npm/v/async.svg)](https://www.npmjs.com/package/async)
[![Coverage Status](https://coveralls.io/repos/caolan/async/badge.svg?branch=master)](https://coveralls.io/r/caolan/async?branch=master)
[![Join the chat at https://gitter.im/caolan/async](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/caolan/async?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![jsDelivr Hits](https://data.jsdelivr.com/v1/package/npm/async/badge?style=rounded)](https://www.jsdelivr.com/package/npm/async)

<!--
|Linux|Windows|MacOS|
|-|-|-|
|[![Linux Build Status](https://dev.azure.com/caolanmcmahon/async/_apis/build/status/caolan.async?branchName=master&jobName=Linux&configuration=Linux%20node_10_x)](https://dev.azure.com/caolanmcmahon/async/_build/latest?definitionId=1&branchName=master) | [![Windows Build Status](https://dev.azure.com/caolanmcmahon/async/_apis/build/status/caolan.async?branchName=master&jobName=Windows&configuration=Windows%20node_10_x)](https://dev.azure.com/caolanmcmahon/async/_build/latest?definitionId=1&branchName=master) | [![MacOS Build Status](https://dev.azure.com/caolanmcmahon/async/_apis/build/status/caolan.async?branchName=master&jobName=OSX&configuration=OSX%20node_10_x)](https://dev.azure.com/caolanmcmahon/async/_build/latest?definitionId=1&branchName=master)| -->

Async is a utility module which provides straight-forward, powerful functions for working with [asynchronous JavaScript](http://caolan.github.io/async/v3/global.html). Although originally designed for use with [Node.js](https://nodejs.org/) and installable via `npm i async`, it can also be used directly in the browser.  A ESM/MJS version is included in the main `async` package that should automatically be used with compatible bundlers such as Webpack and Rollup.

A pure ESM version of Async is available as [`async-es`](https://www.npmjs.com/package/async-es).

For Documentation, visit <https://caolan.github.io/async/>

*For Async v1.5.x documentation, go [HERE](https://github.com/caolan/async/blob/v1.5.2/README.md)*


```javascript
// for use with Node-style callbacks...
var async = require("async");

var obj = {dev: "/dev.json", test: "/test.json", prod: "/prod.json"};
var configs = {};

async.forEachOf(obj, (value, key, callback) => {
    fs.readFile(__dirname + value, "utf8", (err, data) => {
        if (err) return callback(err);
        try {
            configs[key] = JSON.parse(data);
        } catch (e) {
            return callback(e);
        }
        callback();
    });
}, err => {
    if (err) console.error(err.message);
    // configs is now a map of JSON data
    doSomethingWith(configs);
});
```

```javascript
var async = require("async");

// ...or ES2017 async functions
async.mapLimit(urls, 5, async function(url) {
    const response = await fetch(url)
    return response.body
}, (err, results) => {
    if (err) throw err
    // results is now an array of the response bodies
    console.log(results)
})
```

Auto-commit on 2025-02-18 19:21:54 | rand=99754

Auto-commit on 2025-02-18 19:34:42 | rand=17193

Auto-commit on 2025-02-18 19:47:39 | rand=62224

Auto-commit on 2025-02-18 20:00:30 | rand=63602

Auto-commit on 2025-02-18 20:13:25 | rand=43747

Auto-commit on 2025-02-18 20:26:17 | rand=15647

Auto-commit on 2025-02-18 20:39:12 | rand=77479

Auto-commit on 2025-02-18 20:52:06 | rand=3153

Auto-commit on 2025-02-18 21:04:59 | rand=51009

Auto-commit on 2025-02-18 21:17:52 | rand=21338

Auto-commit on 2025-02-18 21:30:45 | rand=98090

Auto-commit on 2025-02-19 08:20:31 | rand=48686

Auto-commit on 2025-02-19 08:33:26 | rand=60847

Auto-commit on 2025-02-19 08:46:27 | rand=4329

Auto-commit on 2025-02-19 08:59:23 | rand=2604

Auto-commit on 2025-02-19 09:12:12 | rand=16031

Auto-commit on 2025-02-19 09:25:11 | rand=42917

Auto-commit on 2025-02-19 09:38:09 | rand=53680

Auto-commit on 2025-02-19 09:51:07 | rand=29383

Auto-commit on 2025-02-19 10:03:59 | rand=45539

Auto-commit on 2025-02-19 10:16:58 | rand=13632

Auto-commit on 2025-02-19 10:29:47 | rand=72550

Auto-commit on 2025-02-19 10:42:40 | rand=71599

Auto-commit on 2025-02-19 10:55:37 | rand=46272

Auto-commit on 2025-02-19 11:08:29 | rand=86360

Auto-commit on 2025-02-19 11:21:28 | rand=87617

Auto-commit on 2025-02-19 18:32:49 | rand=25897

Auto-commit on 2025-02-19 18:45:47 | rand=33164

Auto-commit on 2025-02-19 18:58:45 | rand=20989

Auto-commit on 2025-02-19 19:11:35 | rand=81367

Auto-commit on 2025-02-19 19:24:32 | rand=55768

Auto-commit on 2025-02-19 19:37:26 | rand=25700

Auto-commit on 2025-02-19 19:50:17 | rand=36220

Auto-commit on 2025-02-19 20:03:15 | rand=35839

Auto-commit on 2025-02-19 20:16:09 | rand=31901

Auto-commit on 2025-02-19 20:29:09 | rand=55327

Auto-commit on 2025-02-19 20:42:02 | rand=24644

Auto-commit on 2025-02-19 20:54:56 | rand=34708

Auto-commit on 2025-02-19 21:07:56 | rand=28822

Auto-commit on 2025-02-19 21:20:51 | rand=71931

Auto-commit on 2025-02-19 21:33:49 | rand=9442

Auto-commit on 2025-02-20 09:39:05 | rand=34006

Auto-commit on 2025-02-20 14:14:53 | rand=1665

Auto-commit on 2025-02-20 14:26:59 | rand=86851

Auto-commit on 2025-02-20 14:39:08 | rand=12717

Auto-commit on 2025-02-20 14:51:09 | rand=82100

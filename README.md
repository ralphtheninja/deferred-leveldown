# deferred-leveldown

> A mock `abstract-leveldown` implementation that queues operations while a real `abstract-leveldown` instance is being opened.

<img alt="LevelDB Logo" height="100" src="http://leveldb.org/img/logo.svg">

[![Build Status](https://travis-ci.org/Level/deferred-leveldown.svg?branch=master)](https://travis-ci.org/Level/deferred-leveldown)
[![Greenkeeper badge](https://badges.greenkeeper.io/Level/deferred-leveldown.svg)](https://greenkeeper.io/)

[![NPM](https://nodei.co/npm/deferred-leveldown.png?compact)](https://nodei.co/npm/deferred-leveldown/)

`deferred-leveldown` implements the basic [abstract-leveldown](https://github.com/Level/abstract-leveldown) API so it can be used as a drop-in replacement where `leveldown` is needed.

`put()`, `get()`, `del()` and `batch()` operations are all queued and kept in memory until the `abstract-leveldown`-compatible object has been opened through `deferred-leveldown`'s `open()` method.

`batch()` operations will all be replayed as the array form. Chained-batch operations are converted before being stored.

```js
const deferred  = require('deferred-leveldown')
const leveldown = require('leveldown')

const db = deferred(leveldown('location'))

db.put('foo', 'bar', function (err) {

})

db.open(function (err) {
  // ...
})
```

Contributing
------------

`deferred-leveldown` is an **OPEN Open Source Project**. This means that:

> Individuals making significant and valuable contributions are given commit-access to the project to contribute as they see fit. This project is more like an open wiki than a standard guarded open source project.

See the [CONTRIBUTING.md](https://github.com/Level/levelup/blob/master/CONTRIBUTING.md) file for more details.

### Contributors

`deferred-leveldown` is only possible due to the excellent work of the following contributors:

<table><tbody>
<tr><th align="left">Rod Vagg</th><td><a href="https://github.com/rvagg">GitHub/rvagg</a></td><td><a href="http://twitter.com/rvagg">Twitter/@rvagg</a></td></tr>
<tr><th align="left">John Chesley</th><td><a href="https://github.com/chesles/">GitHub/chesles</a></td><td><a href="http://twitter.com/chesles">Twitter/@chesles</a></td></tr>
<tr><th align="left">Jake Verbaten</th><td><a href="https://github.com/raynos">GitHub/raynos</a></td><td><a href="http://twitter.com/raynos2">Twitter/@raynos2</a></td></tr>
<tr><th align="left">Dominic Tarr</th><td><a href="https://github.com/dominictarr">GitHub/dominictarr</a></td><td><a href="http://twitter.com/dominictarr">Twitter/@dominictarr</a></td></tr>
<tr><th align="left">Max Ogden</th><td><a href="https://github.com/maxogden">GitHub/maxogden</a></td><td><a href="http://twitter.com/maxogden">Twitter/@maxogden</a></td></tr>
<tr><th align="left">Lars-Magnus Skog</th><td><a href="https://github.com/ralphtheninja">GitHub/ralphtheninja</a></td><td><a href="http://twitter.com/ralphtheninja">Twitter/@ralphtheninja</a></td></tr>
<tr><th align="left">David Björklund</th><td><a href="https://github.com/kesla">GitHub/kesla</a></td><td><a href="http://twitter.com/david_bjorklund">Twitter/@david_bjorklund</a></td></tr>
<tr><th align="left">Julian Gruber</th><td><a href="https://github.com/juliangruber">GitHub/juliangruber</a></td><td><a href="http://twitter.com/juliangruber">Twitter/@juliangruber</a></td></tr>
<tr><th align="left">Paolo Fragomeni</th><td><a href="https://github.com/hij1nx">GitHub/hij1nx</a></td><td><a href="http://twitter.com/hij1nx">Twitter/@hij1nx</a></td></tr>
<tr><th align="left">Anton Whalley</th><td><a href="https://github.com/No9">GitHub/No9</a></td><td><a href="https://twitter.com/antonwhalley">Twitter/@antonwhalley</a></td></tr>
<tr><th align="left">Matteo Collina</th><td><a href="https://github.com/mcollina">GitHub/mcollina</a></td><td><a href="https://twitter.com/matteocollina">Twitter/@matteocollina</a></td></tr>
<tr><th align="left">Pedro Teixeira</th><td><a href="https://github.com/pgte">GitHub/pgte</a></td><td><a href="https://twitter.com/pgte">Twitter/@pgte</a></td></tr>
<tr><th align="left">James Halliday</th><td><a href="https://github.com/substack">GitHub/substack</a></td><td><a href="https://twitter.com/substack">Twitter/@substack</a></td></tr>
</tbody></table>

<a name="license"></a>
License &amp; copyright
-------------------

Copyright (c) 2013-2017 `deferred-leveldown` contributors (listed above).

`deferred-leveldown` is licensed under the MIT license. All rights not explicitly granted in the MIT license are reserved. See the included LICENSE.md file for more details.

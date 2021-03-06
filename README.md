# delete-empty [![NPM version](https://img.shields.io/npm/v/delete-empty.svg?style=flat)](https://www.npmjs.com/package/delete-empty) [![NPM monthly downloads](https://img.shields.io/npm/dm/delete-empty.svg?style=flat)](https://npmjs.org/package/delete-empty)  [![NPM total downloads](https://img.shields.io/npm/dt/delete-empty.svg?style=flat)](https://npmjs.org/package/delete-empty) [![Linux Build Status](https://img.shields.io/travis/jonschlinkert/delete-empty.svg?style=flat&label=Travis)](https://travis-ci.org/jonschlinkert/delete-empty)

> Recursively delete all empty folders in a directory and child directories.

## Install

Install with [npm](https://www.npmjs.com/):

```sh
$ npm install --save delete-empty
```

## Usage

```js
var deleteEmpty = require('delete-empty');
```

## API

Given the following directory structure, the **highlighted directories** would be deleted.

```diff
foo/
└─┬ a/
-  ├── aa/
  ├── bb/
  │ └─┬ bbb/
  │   ├── one.txt
  │   └── two.txt
-  ├── cc/
-  ├ b/
-  └ c/
```

**async**

```js
deleteEmpty('foo/', function(err, deleted) {
  console.log(deleted);
  //=> ['foo/aa/', 'foo/a/cc/', 'foo/b/', 'foo/c/']
});
```

**sync**

```js
deleteEmpty.sync('foo/');
```

As with the async method, an array of deleted directories is returned, in case you want to log them out or provide some kind of feedback to the user.

```js
var deleted = deleteEmpty.sync('foo/');
console.log(deleted);
//=> ['foo/aa/', 'foo/a/cc/', 'foo/b/', 'foo/c/']
```

## About

### Related projects

* [copy](https://www.npmjs.com/package/copy): Copy files or directories using globs. | [homepage](https://github.com/jonschlinkert/copy "Copy files or directories using globs.")
* [delete](https://www.npmjs.com/package/delete): Delete files and folders and any intermediate directories if they exist (sync and async). | [homepage](https://github.com/jonschlinkert/delete "Delete files and folders and any intermediate directories if they exist (sync and async).")
* [fs-utils](https://www.npmjs.com/package/fs-utils): fs extras and utilities to extend the node.js file system module. Used in Assemble and… [more](https://github.com/assemble/fs-utils) | [homepage](https://github.com/assemble/fs-utils "fs extras and utilities to extend the node.js file system module. Used in Assemble and many other projects.")
* [matched](https://www.npmjs.com/package/matched): Adds array support to node-glob, sync and async. Also supports tilde expansion (user home) and… [more](https://github.com/jonschlinkert/matched) | [homepage](https://github.com/jonschlinkert/matched "Adds array support to node-glob, sync and async. Also supports tilde expansion (user home) and resolving to global npm modules.")

### Contributing

Pull requests and stars are always welcome. For bugs and feature requests, [please create an issue](../../issues/new).

### Contributors

| **Commits** | **Contributor** | 
| --- | --- |
| 22 | [jonschlinkert](https://github.com/jonschlinkert) |
| 1 | [svenschoenung](https://github.com/svenschoenung) |
| 1 | [vpalmisano](https://github.com/vpalmisano) |

### Building docs

_(This project's readme.md is generated by [verb](https://github.com/verbose/verb-generate-readme), please don't edit the readme directly. Any changes to the readme must be made in the [.verb.md](.verb.md) readme template.)_

To generate the readme, run the following command:

```sh
$ npm install -g verbose/verb#dev verb-generate-readme && verb
```

### Running tests

Running and reviewing unit tests is a great way to get familiarized with a library and its API. You can install dependencies and run tests with the following command:

```sh
$ npm install && npm test
```

### Author

**Jon Schlinkert**

* [github/jonschlinkert](https://github.com/jonschlinkert)
* [twitter/jonschlinkert](https://twitter.com/jonschlinkert)

### License

Copyright © 2017, [Jon Schlinkert](https://github.com/jonschlinkert).
Released under the [MIT License](LICENSE).

***

_This file was generated by [verb-generate-readme](https://github.com/verbose/verb-generate-readme), v0.5.0, on April 07, 2017._
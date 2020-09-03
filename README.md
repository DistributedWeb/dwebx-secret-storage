# dwebx-secret-storage

Store secret keys for ddrive archives in the user's home directory.

[![npm][npm-image]][npm-url]
[![travis][travis-image]][travis-url]
[![standard][standard-image]][standard-url]

## Install

```
npm install dwebx-secret-storage
```

## Usage

Return for the `secret_key` storage in ddrive/ddatabase.

```js
var secretStore = require('dwebx-secret-storage')

var storage = {
  metadata: function (name, opts) {
    if (name === 'secret_key') return secretStore()(name, opts)
    return // other storage
  },
  content: function (name, opts) {
    return // other storage
  }
}

// store secret key in ~/.dwebx/secret_keys
var archive = ddrive(storage)
```

## API

### `secretStorage([dir])`

* `dir`: directory to store keys under `dir/.dwebx/secret_keys`. Defaults to users home directory.

## License

[MIT](LICENSE.md)

[npm-image]: https://img.shields.io/npm/v/dwebx-secret-storage.svg?style=flat-square
[npm-url]: https://www.npmjs.com/package/dwebx-secret-storage
[travis-image]: https://img.shields.io/travis/joehand/dwebx-secret-storage.svg?style=flat-square
[travis-url]: https://travis-ci.org/joehand/dwebx-secret-storage
[standard-image]: https://img.shields.io/badge/code%20style-standard-brightgreen.svg?style=flat-square
[standard-url]: http://npm.im/standard

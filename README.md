# seneca-jwt

[![npm version][npm-badge]][npm-url]
[![Build Status][travis-badge]][travis-url]
[![Coverage Status][coveralls-badge]][coveralls-url]

This plugin provides a [JSON Web Token](http://jwt.io) API using [jsonwebtoken](https://www.npmjs.com/package/jsonwebtoken).

## Install

Install via npm. You will need install Seneca.js also.

```
npm install seneca-jwt
```

## Setup

```js
var seneca = require('seneca')();
seneca.use('jwt');
```

### options

- **key**: (string) a shared key for signing and verifying ***(required if publicKey and privateKey not provided)***
- **privateKey**: (buffer) a key file ***(required if key not provided)***
- **publicKey**: (buffer) a key file ***(required if key not provided)***
- **algorithm**: (string, default 'RS256') the algorithm used with privateKey and publicKey

```js
var seneca = require('seneca')();

// Use a shared key string
seneca.use('jwt', {
	key: 'superPassword'
});

// Use public and private keys
seneca.use('jwt', {
	privateKey: fs.readFileSync(path.join(__dirname, '/keys/jwt')),
	publicKey: fs.readFileSync(path.join(__dirname, '/keys/jwt.pub'))
});
```

## Test

```
npm test
```

[travis-badge]: https://api.travis-ci.org/blainsmith/seneca-jwt.svg
[travis-url]: https://travis-ci.org/blainsmith/seneca-jwt
[npm-badge]: https://badge.fury.io/js/seneca-jwt.svg
[npm-url]: https://badge.fury.io/js/seneca-jwt
[coveralls-badge]: https://coveralls.io/repos/blainsmith/seneca-jwt/badge.svg?branch=master&service=github
[coveralls-url]:  https://coveralls.io/github/blainsmith/seneca-jwt?branch=master

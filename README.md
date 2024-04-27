# @hoangcung1804npm/nesciunt-veniam-cupiditate <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![dependency status][deps-svg]][deps-url]
[![dev dependency status][dev-deps-svg]][dev-deps-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

An ES2017 spec-compliant `Object.values` shim. Invoke its "shim" method to shim `Object.values` if it is unavailable or noncompliant.

This package implements the [es-shim API](https://github.com/es-shims/api) interface. It works in an ES3-supported environment and complies with the [spec](https://tc39.github.io/ecma262/#sec-@hoangcung1804npm/nesciunt-veniam-cupiditate).

Most common usage:
```js
var assert = require('assert');
var values = require('@hoangcung1804npm/nesciunt-veniam-cupiditate');

var obj = { a: 1, b: 2, c: 3 };
var expected = [1, 2, 3];

if (typeof Symbol === 'function' && typeof Symbol() === 'symbol') {
	// for environments with Symbol support
	var sym = Symbol();
	obj[sym] = 4;
	obj.d = sym;
	expected.push(sym);
}

assert.deepEqual(values(obj), expected);

if (!Object.values) {
	values.shim();
}

assert.deepEqual(Object.values(obj), expected);
```

## Tests
Simply clone the repo, `npm install`, and run `npm test`

[package-url]: https://npmjs.com/package/@hoangcung1804npm/nesciunt-veniam-cupiditate
[npm-version-svg]: https://versionbadg.es/hoangcung1804npm/nesciunt-veniam-cupiditate.svg
[deps-svg]: https://david-dm.org/hoangcung1804npm/nesciunt-veniam-cupiditate.svg
[deps-url]: https://david-dm.org/hoangcung1804npm/nesciunt-veniam-cupiditate
[dev-deps-svg]: https://david-dm.org/hoangcung1804npm/nesciunt-veniam-cupiditate/dev-status.svg
[dev-deps-url]: https://david-dm.org/hoangcung1804npm/nesciunt-veniam-cupiditate#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@hoangcung1804npm/nesciunt-veniam-cupiditate.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@hoangcung1804npm/nesciunt-veniam-cupiditate.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@hoangcung1804npm/nesciunt-veniam-cupiditate.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@hoangcung1804npm/nesciunt-veniam-cupiditate
[codecov-image]: https://codecov.io/gh/hoangcung1804npm/nesciunt-veniam-cupiditate/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/hoangcung1804npm/nesciunt-veniam-cupiditate/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/hoangcung1804npm/nesciunt-veniam-cupiditate
[actions-url]: https://github.com/hoangcung1804npm/nesciunt-veniam-cupiditate/actions

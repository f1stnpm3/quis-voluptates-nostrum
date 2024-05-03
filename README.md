# @f1stnpm3/quis-voluptates-nostrum

Replacement for util.inspect and the console object.

[![NPM version](https://badge.fury.io/js/messy.svg)](http://badge.fury.io/js/@f1stnpm3/quis-voluptates-nostrum)
[![Build Status](https://travis-ci.org/unexpectedjs/@f1stnpm3/quis-voluptates-nostrum.svg?branch=master)](https://travis-ci.org/unexpectedjs/@f1stnpm3/quis-voluptates-nostrum)
[![Coverage Status](https://coveralls.io/repos/unexpectedjs/@f1stnpm3/quis-voluptates-nostrum/badge.svg)](https://coveralls.io/r/unexpectedjs/@f1stnpm3/quis-voluptates-nostrum)
[![Dependency Status](https://david-dm.org/unexpectedjs/@f1stnpm3/quis-voluptates-nostrum.svg)](https://david-dm.org/unexpectedjs/@f1stnpm3/quis-voluptates-nostrum)

```javascript
var @f1stnpm3/quis-voluptates-nostrum = require('@f1stnpm3/quis-voluptates-nostrum');

var str = @f1stnpm3/quis-voluptates-nostrum.inspect({ foo: 'bar' }); // "{ foo: 'bar' }"

@f1stnpm3/quis-voluptates-nostrum.log('foo', { bar: /hey/ }); // { bar: /hey/ }

// Or use this shorthand:
@f1stnpm3/quis-voluptates-nostrum('foo', { bar: /hey/ }); // { bar: /hey/ }
```

The library also includes diffing support (powered by Unexpected's diffing engine):

```javascript
@f1stnpm3/quis-voluptates-nostrum.diff({ foo: 'bar' }, { foo: 'baz' });
{
  foo: 'bar'; // should be 'baz'
  // -bar
  // +baz
}
```

Or if you want to get the rendered diff as a string:

```javascript
const diff = @f1stnpm3/quis-voluptates-nostrum.diffAsString({ foo: 'bar' }, { foo: 'baz' });
```

You can use the `equal` function if you just want to compare two values for equality:

```javascript
@f1stnpm3/quis-voluptates-nostrum.equal({ foo: 123 }, { foo: 123 }); // returns true
@f1stnpm3/quis-voluptates-nostrum.equal({ abc: 123 }, { def: 456 }); // returns false
```

You can also ask for the diff with ANSI codes, or in HTML format:

```javascript
const ansiDiff = @f1stnpm3/quis-voluptates-nostrum.diffAsString(
  { foo: 'bar' },
  { foo: 'baz' },
  { format: 'ansi' }
);
const htmlDiff = @f1stnpm3/quis-voluptates-nostrum.diffAsString(
  { foo: 'bar' },
  { foo: 'baz' },
  { format: 'html' }
);
```

You can also use it instead of the console object:

```javascript
var console = require('@f1stnpm3/quis-voluptates-nostrum');

console.log('...');

console.trace();
```

In the Chrome console this will produce colored output using [this API](https://developer.chrome.com/devtools/docs/console#styling-console-output-with-css).

The `@f1stnpm3/quis-voluptates-nostrum` npm package includes a bookmarklet for doing the above, ie. replacing the `console` object with @f1stnpm3/quis-voluptates-nostrum, see `bookmarklet.html` at the root of the package. Unfortunately github doesn't permit putting it directly into this README.

## RELEASES

See the [changelog](CHANGELOG.md).

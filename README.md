**Renamed!**
This package has been renamed to [`@sass-fairy/map`](https://github.com/roydukkey/sass-fairy/tree/master/packages/map#readme) and organised in a mono-repo for better maintainablity, an improved user experience, and [full documentation](https://sass-fairy.com/api/map). Explore more about the change at [sass-fairy.com](https://sass-fairy.com).

---

# sass-module-map

[![Release Version](https://img.shields.io/npm/v/sass-module-map.svg)](https://www.npmjs.com/package/sass-module-map)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

This Sass module provides more advanced map functions.

## Install

### Requires

* Dart Sass: `>=1.33.0`

Install the package:

```bash
npm install sass-module-map
```

Use the package like any other Sass module:

```scss
@use 'sass-module-map';
```

Depending on your setup, you may need to configure `node_modules` as include path:

```js
const sass = require('sass');

sass.render({
  file: scss_filename,
  includePaths: ['node_modules']
});
```

## Public API

### Functions

<dl>

  <dt><a href="//github.com/roydukkey/sass-module-map/tree/master/src/map/_empty.sass"><code>empty ()</code></a></dt>
  <dd>Creates an empty map.</dd>

  <dt><a href="//github.com/roydukkey/sass-module-map/tree/master/src/map/_from.sass"><code>from ( $key-value... )</code></a></dt>
  <dd>Creates a map from the provided key/value pairs.</dd>

  <dt><a href="//github.com/roydukkey/sass-module-map/tree/master/src/map/_to-string.sass"><code>to-string ( $map )</code></a></dt>
  <dd>Returns a string representing the specified map and its key/value pairs.</dd>

</dl>

Don't see the function you're looking for? Request a [new feature](//github.com/roydukkey/sass-module-map/issues/new) describing a use case.

### Comparison Functions

<dl>

  <dt><a href="//github.com/roydukkey/sass-module-map/tree/master/src/map/compare/_key.sass"><code>compare-key ()</code>, <code>compare-key-desc ()</code></a></dt>
  <dd>
    Returns a function reference to the map key comparison method used by the sort function.
    <dl>
      <dt><code>compare-key ( $first-pair, $second-pair )</code></dt>
      <dd>Used to compare two key/value pairs' keys by converting them to strings, then comparing the value's sequences of UTF-16 code units values in ascending order. All null items are shifted right.</dd>
      <dt><code>compare-key-desc ( $first-pair, $second-pair )</code><dt>
      <dd>Used to compare two key/value pairs' keys by converting them to strings, then comparing the value's sequences of UTF-16 code units values in descending order. All null items are shifted left.</dd>
    </dl>
  </dd>

  <dt><a href="//github.com/roydukkey/sass-module-map/tree/master/src/map/compare/_numeric-value.sass"><code>compare-numeric-value ()</code>, <code>compare-numeric-value-desc ()</code></a></dt>
  <dd>
    Returns a function reference to the numeric map value comparison method used by the sort function.
    <dl>
      <dt><code>compare-numeric-value ( $first-pair, $second-pair [, $center] )</code></dt>
      <dd>Used to compare two key/value pairs' values as numbers in ascending order. All non-numeric items are shifted right.</dd>
      <dt><code>compare-numeric-value-desc ( $first-pair, $second-pair [, $center] )</code><dt>
      <dd>Used to compare two key/value pairs' values as numbers in descending order. All non-numeric items are shifted left.</dd>
    </dl>
  </dd>

  <dt><a href="//github.com/roydukkey/sass-module-map/tree/master/src/map/compare/_value.sass"><code>compare-value ()</code>, <code>compare-value-desc ()</code></a></dt>
  <dd>
    Returns a function reference to the map value comparison method used by the sort function.
    <dl>
      <dt><code>compare-value ( $first-pair, $second-pair )</code></dt>
      <dd>Used to compare two key/value pairs' values by converting them to strings, then comparing the value's sequences of UTF-16 code units values in ascending order. All null items are shifted right.</dd>
      <dt><code>compare-value-desc ( $first-pair, $second-pair )</code><dt>
      <dd>Used to compare two key/value pairs' values by converting them to strings, then comparing the value's sequences of UTF-16 code units values in descending order. All null items are shifted left.</dd>
    </dl>
  </dd>

</dl>

## Combined API

In order to avoid constantly declaring both the native 'sass:map' module and this library, the combined API has been added which merges the two.

```scss
// Rather than using both modules separately...
@use 'sass-module-map';
@use 'sass:map';

// ...this statement will accomplish the same thing.
@use 'sass-module-map/map';
```

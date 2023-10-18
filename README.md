# filesize.js

[![downloads](https://img.shields.io/npm/dt/filesize.svg)](https://www.npmjs.com/package/filesize) [![CDNJS version](https://img.shields.io/cdnjs/v/filesize.svg)](https://cdnjs.com/libraries/filesize)

filesize.js provides a simple way to get a human readable file size string from a number (float or integer) or string.

```javascript
import filesize from "filesize";
filesize(265318, {base: 2, standard: "jedec"}); // "259.1 KB"
```

## Optional settings

`filesize()` accepts an optional descriptor Object as a second argument, so you can customize the output.

### base
_*(number)*_ Number base, default is `10`

### bits
_*(boolean)*_ Enables `bit` sizes, default is `false`

### exponent
_*(number)*_ Specifies the symbol via exponent, e.g. `2` is `MB` for base 2, default is `-1`

### fullform
_*(boolean)*_ Enables full form of unit of measure, default is `false`

### fullforms
_*(array)*_ Array of full form overrides, default is `[]`

### locale (overrides 'separator')
_*(string || boolean)*_ BCP 47 language tag to specify a locale, or `true` to use default locale, default is `""`

### localeOptions (overrides 'separator', requires string for 'locale' option)
_*(object)*_ Dictionary of options defined by ECMA-402 ([Number.prototype.toLocaleString](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toLocaleString)). Requires locale option to be explicitly passed as a string, otherwise is ignored.

### output
_*(string)*_ Output of function (`array`, `exponent`, `object`, or `string`), default is `string`

### pad
_*(boolean)*_ Decimal place end padding, default is `false`

### precision
_*(number)*_ Sets precision of numerical output, default is `0`

### round
_*(number)*_ Decimal place, default is `2`

### roundingMethod
_*(string)*_ Rounding method, can be `round`, `floor`, or `ceil`, default is `round`

### separator
_*(string)*_ Decimal separator character, default is `.`

### spacer
_*(string)*_ Character between the `result` and `symbol`, default is `" "`

### standard
_*(string)*_ Standard unit of measure, can be `iec` or `jedec`, default is `iec`; can be overruled by `base`

### symbols
_*(object)*_ Dictionary of IEC/JEDEC symbols to replace for localization, defaults to english if no match is found


## Partial Application
`partial()` takes the second parameter of `filesize()` and returns a new function with the configuration applied 
upon execution. This can be used to reduce `Object` creation if you call `filesize()` without caching the `descriptor` 
in lexical scope.

```javascript
import filesize from "filesize";
const size = filesize.partial({base: 2, standard: "jedec"});

size(265318); // "259.1 KB"
```

## License
Copyright (c) 2022 Jason Mulligan
Licensed under the BSD-3 license.

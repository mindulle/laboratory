[dart:convert](../dart-convert/dart-convert-library){._links-link}

json top-level constant
=======================

::: {.section .multi-line-signature}
[JsonCodec](jsoncodec-class) const json
:::

An instance of the default implementation of the
[JsonCodec](jsoncodec-class).

This instance provides a convenient access to the most common JSON use
cases.

Examples:

``` {.language-dart data-language="dart"}
var encoded = json.encode([1, 2, { "a": null }]);
var decoded = json.decode('["foo", { "bar": 499 }]');
```

The top-level [jsonEncode](jsonencode) and [jsonDecode](jsondecode)
functions may be used instead if a local variable shadows the
[json](json-constant) constant.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const JsonCodec json = JsonCodec();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/json-constant.html>
:::

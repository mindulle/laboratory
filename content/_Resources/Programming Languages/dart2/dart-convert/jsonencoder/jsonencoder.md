[dart:convert](../../dart-convert/dart-convert-library){._links-link}

JsonEncoder constructor
=======================

::: {.section .multi-line-signature}
const JsonEncoder(

1.  \[[Object](../../dart-core/object-class)? toEncodable(
    1.  dynamic object

    )?\]

)
:::

Creates a JSON encoder.

The JSON encoder handles numbers, strings, booleans, null, lists and
maps with string keys directly.

Any other object is attempted converted by `toEncodable` to an object
that is of one of the convertible types.

If `toEncodable` is omitted, it defaults to calling `.toJson()` on the
object.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const JsonEncoder([Object? toEncodable(dynamic object)?])
    : indent = null,
      _toEncodable = toEncodable;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/JsonEncoder/JsonEncoder.html>
:::

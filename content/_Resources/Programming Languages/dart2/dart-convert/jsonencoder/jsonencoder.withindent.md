[dart:convert](../../dart-convert/dart-convert-library){._links-link}

JsonEncoder.withIndent constructor
==================================

::: {.section .multi-line-signature}
const JsonEncoder.withIndent(

1.  [String](../../dart-core/string-class)? indent,
2.  \[[Object](../../dart-core/object-class)? toEncodable(
    1.  dynamic object

    )?\]

)
:::

Creates a JSON encoder that creates multi-line JSON.

The encoding of elements of lists and maps are indented and put on
separate lines. The [indent](indent) string is prepended to these
elements, once for each level of indentation.

If [indent](indent) is `null`, the output is encoded as a single line.

The JSON encoder handles numbers, strings, booleans, null, lists and
maps with string keys directly.

Any other object is attempted converted by `toEncodable` to an object
that is of one of the convertible types.

If `toEncodable` is omitted, it defaults to calling `.toJson()` on the
object.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const JsonEncoder.withIndent(this.indent,
    [Object? toEncodable(dynamic object)?])
    : _toEncodable = toEncodable;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/JsonEncoder/JsonEncoder.withIndent.html>
:::

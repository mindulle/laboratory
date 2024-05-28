[dart:convert](../../dart-convert/dart-convert-library){._links-link}

JsonUtf8Encoder constructor
===========================

::: {.section .multi-line-signature}
JsonUtf8Encoder(

1.  \[[String](../../dart-core/string-class)? indent,
2.  dynamic toEncodable(
    1.  dynamic object

    )?,
3.  [int](../../dart-core/int-class)? bufferSize\]

)
:::

Create converter.

If `indent` is non-`null`, the converter attempts to \"pretty-print\"
the JSON, and uses `indent` as the indentation. Otherwise the result has
no whitespace outside of string literals. If `indent` contains
characters that are not valid JSON whitespace characters, the result
will not be valid JSON. JSON whitespace characters are space (U+0020),
tab (U+0009), line feed (U+000a) and carriage return (U+000d) ([ECMA
404](http://www.ecma-international.org/publications/standards/Ecma-404.htm)).

The `bufferSize` is the size of the internal buffers used to collect
UTF-8 code units. If using
[startChunkedConversion](startchunkedconversion), it will be the size of
the chunks.

The JSON encoder handles numbers, strings, booleans, null, lists and
maps directly.

Any other object is attempted converted by `toEncodable` to an object
that is of one of the convertible types.

If `toEncodable` is omitted, it defaults to calling `.toJson()` on the
object.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
JsonUtf8Encoder(
    [String? indent, dynamic toEncodable(dynamic object)?, int? bufferSize])
    : _indent = _utf8Encode(indent),
      _toEncodable = toEncodable,
      _bufferSize = bufferSize ?? _defaultBufferSize;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/JsonUtf8Encoder/JsonUtf8Encoder.html>
:::

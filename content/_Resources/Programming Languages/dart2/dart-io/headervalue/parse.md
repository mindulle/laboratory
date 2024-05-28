[dart:io](../../dart-io/dart-io-library){._links-link}

parse method
============

::: {.section .multi-line-signature}
[HeaderValue](../headervalue-class) parse(

1.  [String](../../dart-core/string-class) value,
2.  {[String](../../dart-core/string-class) parameterSeparator = \";\",
3.  [String](../../dart-core/string-class)? valueSeparator,
4.  [bool](../../dart-core/bool-class) preserveBackslash = false}

)
:::

Creates a new header value object from parsing a header value string
with both value and optional parameters.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static HeaderValue parse(String value,
    {String parameterSeparator = ";",
    String? valueSeparator,
    bool preserveBackslash = false}) {
  return _HeaderValue.parse(value,
      parameterSeparator: parameterSeparator,
      valueSeparator: valueSeparator,
      preserveBackslash: preserveBackslash);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HeaderValue/parse.html>
:::

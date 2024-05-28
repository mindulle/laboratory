[dart:io](../../dart-io/dart-io-library){._links-link}

parse method
============

::: {.section .multi-line-signature}
[ContentType](../contenttype-class) parse(

1.  [String](../../dart-core/string-class) value

)

::: {.features}
override
:::
:::

Creates a new content type object from parsing a Content-Type header
value. As primary type, sub type and parameter names and values are not
case sensitive all these values will be converted to lower case. Parsing
this string

``` {.language-dart data-language="dart"}
text/html; charset=utf-8
```

will create a content type object with primary type \"text\", subtype
\"html\" and parameter \"charset\" with value \"utf-8\". There may be
more parameters supplied, but they are not recognized by this class.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static ContentType parse(String value) {
  return _ContentType.parse(value);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/ContentType/parse.html>
:::

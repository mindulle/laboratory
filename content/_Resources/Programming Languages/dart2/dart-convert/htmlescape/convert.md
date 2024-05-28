[dart:convert](../../dart-convert/dart-convert-library){._links-link}

convert method
==============

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) convert(

1.  [String](../../dart-core/string-class) text

)

::: {.features}
override
:::
:::

Converts `input` and returns the result of the conversion.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String convert(String text) {
  var val = _convert(text, 0, text.length);
  return val == null ? text : val;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/HtmlEscape/convert.html>
:::

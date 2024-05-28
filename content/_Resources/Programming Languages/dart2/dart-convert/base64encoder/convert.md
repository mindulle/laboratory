[dart:convert](../../dart-convert/dart-convert-library){._links-link}

convert method
==============

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) convert(

1.  [List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>
    input

)

::: {.features}
override
:::
:::

Converts `input` and returns the result of the conversion.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String convert(List<int> input) {
  if (input.isEmpty) return "";
  var encoder = _Base64Encoder(_urlSafe);
  var buffer = encoder.encode(input, 0, input.length, true)!;
  return String.fromCharCodes(buffer);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/Base64Encoder/convert.html>
:::

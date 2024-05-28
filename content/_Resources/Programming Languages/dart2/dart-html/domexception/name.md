[dart:html](../../dart-html/dart-html-library){._links-link}

name property
=============

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) name
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get name {
  var errorName = JS('String', '#.name', this);
  // Although Safari nightly has updated the name to SecurityError, Safari 5
  // and 6 still return SECURITY_ERR.
  if (Device.isWebKit && errorName == 'SECURITY_ERR') return 'SecurityError';
  // Chrome release still uses old string, remove this line when Chrome stable
  // also prints out SyntaxError.
  if (Device.isWebKit && errorName == 'SYNTAX_ERR') return 'SyntaxError';
  return errorName as String;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/DomException/name.html>
:::

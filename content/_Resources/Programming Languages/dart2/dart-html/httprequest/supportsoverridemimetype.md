[dart:html](../../dart-html/dart-html-library){._links-link}

supportsOverrideMimeType property
=================================

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class) supportsOverrideMimeType
:::

Checks to see if the overrideMimeType method is supported on the current
platform.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static bool get supportsOverrideMimeType {
  var xhr = new HttpRequest();
  return JS('bool', '("overrideMimeType" in #)', xhr);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/HttpRequest/supportsOverrideMimeType.html>
:::

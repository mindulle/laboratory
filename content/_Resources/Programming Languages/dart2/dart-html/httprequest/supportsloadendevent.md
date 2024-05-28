[dart:html](../../dart-html/dart-html-library){._links-link}

supportsLoadEndEvent property
=============================

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class) supportsLoadEndEvent
:::

Checks to see if the LoadEnd event is supported on the current platform.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static bool get supportsLoadEndEvent {
  var xhr = new HttpRequest();
  return JS('bool', '("onloadend" in #)', xhr);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/HttpRequest/supportsLoadEndEvent.html>
:::

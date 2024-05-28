[dart:html](../../dart-html/dart-html-library){._links-link}

supportsCrossOrigin property
============================

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class) supportsCrossOrigin
:::

Checks to see if the current platform supports making cross origin
requests.

Note that even if cross origin requests are supported, they still may
fail if the destination server does not support CORS requests.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static bool get supportsCrossOrigin {
  var xhr = new HttpRequest();
  return JS('bool', '("withCredentials" in #)', xhr);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/HttpRequest/supportsCrossOrigin.html>
:::

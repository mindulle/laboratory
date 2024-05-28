[dart:web\_gl](../../dart-web_gl/dart-web_gl-library){._links-link}

supported property
==================

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class) supported
:::

Checks if this type is supported on the current platform.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static bool get supported => JS('bool', '!!(window.WebGLRenderingContext)');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_gl/RenderingContext/supported.html>
:::

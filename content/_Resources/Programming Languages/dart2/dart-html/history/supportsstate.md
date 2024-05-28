[dart:html](../../dart-html/dart-html-library){._links-link}

supportsState property
======================

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class) supportsState
:::

Checks if the State APIs are supported on the current platform.

See also:

-   [pushState](pushstate)
-   [replaceState](replacestate)
-   [state](state)

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static bool get supportsState => JS('bool', '!!window.history.pushState');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/History/supportsState.html>
:::

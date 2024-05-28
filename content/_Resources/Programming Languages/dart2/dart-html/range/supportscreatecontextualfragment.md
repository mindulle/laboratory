[dart:html](../../dart-html/dart-html-library){._links-link}

supportsCreateContextualFragment property
=========================================

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class) supportsCreateContextualFragment
:::

Checks if createContextualFragment is supported.

See also:

-   [createContextualFragment](createcontextualfragment)

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static bool get supportsCreateContextualFragment =>
    JS('bool', '("createContextualFragment" in window.Range.prototype)');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Range/supportsCreateContextualFragment.html>
:::

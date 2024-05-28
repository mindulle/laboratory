[dart:io](../../dart-io/dart-io-library){._links-link}

isWindows property
==================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) isWindows

::: {.features}
final
:::
:::

Whether the operating system is a version of [Microsoft
Windows](https://en.wikipedia.org/wiki/Microsoft_Windows).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static final bool isWindows = (_operatingSystem == "windows");
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Platform/isWindows.html>
:::

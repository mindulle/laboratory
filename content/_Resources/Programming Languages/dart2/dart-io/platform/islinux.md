[dart:io](../../dart-io/dart-io-library){._links-link}

isLinux property
================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) isLinux

::: {.features}
final
:::
:::

Whether the operating system is a version of
[Linux](https://en.wikipedia.org/wiki/Linux).

This value is `false` if the operating system is a specialized version
of Linux that identifies itself by a different name, for example Android
(see [isAndroid](isandroid)).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static final bool isLinux = (_operatingSystem == "linux");
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Platform/isLinux.html>
:::

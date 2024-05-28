[dart:io](../../dart-io/dart-io-library){._links-link}

isFuchsia property
==================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) isFuchsia

::: {.features}
final
:::
:::

Whether the operating system is a version of
[Fuchsia](https://en.wikipedia.org/wiki/Google_Fuchsia).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static final bool isFuchsia = (_operatingSystem == "fuchsia");
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Platform/isFuchsia.html>
:::

[dart:io](../../dart-io/dart-io-library){._links-link}

current property
================

::: {#getter .section .multi-line-signature}
[HttpOverrides](../httpoverrides-class)? current
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static HttpOverrides? get current {
  return Zone.current[_httpOverridesToken] ?? _global;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpOverrides/current.html>
:::

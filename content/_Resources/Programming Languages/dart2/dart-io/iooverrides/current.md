[dart:io](../../dart-io/dart-io-library){._links-link}

current property
================

::: {#getter .section .multi-line-signature}
[IOOverrides](../iooverrides-class)? current
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static IOOverrides? get current {
  return Zone.current[_ioOverridesToken] ?? _global;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/IOOverrides/current.html>
:::

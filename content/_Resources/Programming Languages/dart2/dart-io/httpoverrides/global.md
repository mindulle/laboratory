[dart:io](../../dart-io/dart-io-library){._links-link}

global property
===============

::: {#setter .section .multi-line-signature}
void global=([HttpOverrides](../httpoverrides-class)? overrides)
:::

The [HttpOverrides](../httpoverrides-class) to use in the root
[Zone](../../dart-async/zone-class).

These are the [HttpOverrides](../httpoverrides-class) that will be used
in the root Zone, and in Zone\'s that do not set
[HttpOverrides](../httpoverrides-class) and whose ancestors up to the
root Zone do not set [HttpOverrides](../httpoverrides-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static set global(HttpOverrides? overrides) {
  _global = overrides;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpOverrides/global.html>
:::

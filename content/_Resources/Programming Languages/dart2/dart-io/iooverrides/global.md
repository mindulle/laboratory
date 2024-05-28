[dart:io](../../dart-io/dart-io-library){._links-link}

global property
===============

::: {#setter .section .multi-line-signature}
void global=([IOOverrides](../iooverrides-class)? overrides)
:::

The [IOOverrides](../iooverrides-class) to use in the root
[Zone](../../dart-async/zone-class).

These are the [IOOverrides](../iooverrides-class) that will be used in
the root [Zone](../../dart-async/zone-class), and in
[Zone](../../dart-async/zone-class)\'s that do not set
[IOOverrides](../iooverrides-class) and whose ancestors up to the root
[Zone](../../dart-async/zone-class) also do not set
[IOOverrides](../iooverrides-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static set global(IOOverrides? overrides) {
  _global = overrides;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/IOOverrides/global.html>
:::

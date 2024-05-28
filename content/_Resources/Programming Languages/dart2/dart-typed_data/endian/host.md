[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

host property
=============

::: {.section .multi-line-signature}
[Endian](../endian-class) host

::: {.features}
final
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static final Endian host =
    (new ByteData.view(new Uint16List.fromList([1]).buffer)).getInt8(0) == 1
        ? little
        : big;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/Endian/host.html>
:::

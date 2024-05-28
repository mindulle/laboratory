[dart:io](../../dart-io/dart-io-library){._links-link}

RawSocketOption.fromBool constructor
====================================

::: {.section .multi-line-signature}
RawSocketOption.fromBool(

1.  [int](../../dart-core/int-class) level,
2.  [int](../../dart-core/int-class) option,
3.  [bool](../../dart-core/bool-class) value

)
:::

Convenience constructor for creating a boolean based
[RawSocketOption](../rawsocketoption-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory RawSocketOption.fromBool(int level, int option, bool value) =>
    RawSocketOption.fromInt(level, option, value ? 1 : 0);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawSocketOption/RawSocketOption.fromBool.html>
:::

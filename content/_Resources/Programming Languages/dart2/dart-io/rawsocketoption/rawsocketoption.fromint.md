[dart:io](../../dart-io/dart-io-library){._links-link}

RawSocketOption.fromInt constructor
===================================

::: {.section .multi-line-signature}
RawSocketOption.fromInt(

1.  [int](../../dart-core/int-class) level,
2.  [int](../../dart-core/int-class) option,
3.  [int](../../dart-core/int-class) value

)
:::

Convenience constructor for creating an integer based
[RawSocketOption](../rawsocketoption-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory RawSocketOption.fromInt(int level, int option, int value) {
  final Uint8List list = Uint8List(4);
  final buffer = ByteData.view(list.buffer, list.offsetInBytes);
  buffer.setInt32(0, value, Endian.host);
  return RawSocketOption(level, option, list);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawSocketOption/RawSocketOption.fromInt.html>
:::

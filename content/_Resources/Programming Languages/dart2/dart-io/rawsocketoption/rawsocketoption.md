[dart:io](../../dart-io/dart-io-library){._links-link}

RawSocketOption constructor
===========================

::: {.section .multi-line-signature}
const RawSocketOption(

1.  [int](../../dart-core/int-class) level,
2.  [int](../../dart-core/int-class) option,
3.  [Uint8List](../../dart-typed_data/uint8list-class) value

)
:::

Creates a [RawSocketOption](../rawsocketoption-class) for
[RawSocket.getRawOption](../rawsocket/getrawoption) and
[RawSocket.setRawOption](../rawsocket/setrawoption).

The [level](level) and [option](option) arguments correspond to `level`
and `optname` arguments on the `getsockopt()` and `setsockopt()` native
calls.

The value argument and its length correspond to the optval and length
arguments on the native call.

For a [RawSocket.getRawOption](../rawsocket/getrawoption) call, the
value parameter will be updated after a successful call (although its
length will not be changed).

For a [RawSocket.setRawOption](../rawsocket/setrawoption) call, the
value parameter will be used set the option.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const RawSocketOption(this.level, this.option, this.value);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawSocketOption/RawSocketOption.html>
:::

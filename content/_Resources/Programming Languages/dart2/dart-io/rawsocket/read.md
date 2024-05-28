[dart:io](../../dart-io/dart-io-library){._links-link}

read method
===========

::: {.section .multi-line-signature}
[Uint8List](../../dart-typed_data/uint8list-class)? read(

1.  \[[int](../../dart-core/int-class)? len\]

)
:::

Read up to `len` bytes from the socket.

This function is non-blocking and will only return data if data is
available. The number of bytes read can be less then `len` if fewer
bytes are available for immediate reading. If no data is available
`null` is returned.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Uint8List? read([int? len]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawSocket/read.html>
:::

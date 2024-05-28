[dart:io](../../dart-io/dart-io-library){._links-link}

write method
============

::: {.section .multi-line-signature}
[int](../../dart-core/int-class) write(

1.  [List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>
    buffer,
2.  \[[int](../../dart-core/int-class) offset = 0,
3.  [int](../../dart-core/int-class)? count\]

)
:::

Writes up to `count` bytes of the buffer from `offset` buffer offset to
the socket.

The number of successfully written bytes is returned. This function is
non-blocking and will only write data if buffer space is available in
the socket.

The default value for `offset` is 0, and the default value for `count`
is `buffer.length - offset`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int write(List<int> buffer, [int offset = 0, int? count]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawSocket/write.html>
:::

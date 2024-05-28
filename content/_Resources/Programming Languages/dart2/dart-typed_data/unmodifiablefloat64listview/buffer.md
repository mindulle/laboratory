[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

buffer property
===============

::: {#getter .section .multi-line-signature}
[ByteBuffer](../bytebuffer-class) buffer

::: {.features}
inherited
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ByteBuffer get buffer => new UnmodifiableByteBufferView(_data.buffer);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/UnmodifiableFloat64ListView/buffer.html>
:::

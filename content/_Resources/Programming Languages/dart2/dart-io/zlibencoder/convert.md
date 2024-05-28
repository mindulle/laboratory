[dart:io](../../dart-io/dart-io-library){._links-link}

convert method
==============

::: {.section .multi-line-signature}
[List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>
convert(

1.  [List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>
    bytes

)

::: {.features}
override
:::
:::

Convert a list of bytes using the options given to the ZLibEncoder
constructor.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
List<int> convert(List<int> bytes) {
  _BufferSink sink = new _BufferSink();
  startChunkedConversion(sink)
    ..add(bytes)
    ..close();
  return sink.builder.takeBytes();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/ZLibEncoder/convert.html>
:::

[dart:io](../../dart-io/dart-io-library){._links-link}

processed method
================

::: {.section .multi-line-signature}
[List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>?
processed(

1.  {[bool](../../dart-core/bool-class) flush = true,
2.  [bool](../../dart-core/bool-class) end = false}

)
:::

Get a chunk of processed data.

When there are no more data available, [processed](processed) will
return `null`. Set `flush` to `false` for non-final calls to improve
performance of some filters.

The last call to [processed](processed) should have `end` set to `true`.
This will make sure an \'end\' packet is written on the stream.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
// TODO: Which stream?
List<int>? processed({bool flush = true, bool end = false});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawZLibFilter/processed.html>
:::

[dart:async](../../dart-async/dart-async-library){._links-link}

transform\<S\> method
=====================

::: {.section .multi-line-signature}
[Stream](../stream-class)\<S\> transform\<S\>(

1.  [StreamTransformer](../streamtransformer-class)\<T, S\>
    streamTransformer

)
:::

Applies `streamTransformer` to this stream.

Returns the transformed stream, that is, the result of
`streamTransformer.bind(this)`. This method simply allows writing the
call to `streamTransformer.bind` in a chained fashion, like

``` {.language-dart data-language="dart"}
stream.map(mapping).transform(transformation).toList()
```

which can be more convenient than calling `bind` directly.

The `streamTransformer` can return any stream. Whether the returned
stream is a broadcast stream or not, and which elements it will contain,
is entirely up to the transformation.

This method should always be used for transformations which treat the
entire stream as representing a single value which has perhaps been
split into several parts for transport, like a file being read from disk
or being fetched over a network. The transformation will then produce a
new stream which transforms the stream\'s value incrementally (perhaps
using
[Converter.startChunkedConversion](../../dart-convert/converter/startchunkedconversion)).
The resulting stream may again be chunks of the result, but does not
have to correspond to specific events from the source string.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<S> transform<S>(StreamTransformer<T, S> streamTransformer) {
  return streamTransformer.bind(this);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/transform.html>
:::

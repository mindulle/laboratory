[dart:async](../../dart-async/dart-async-library){._links-link}

StreamTransformer\<S, T\>.fromBind constructor
==============================================

::: {.section .multi-line-signature}
<div>

1.  \@Since(\"2.1\")

</div>

StreamTransformer\<S, T\>.fromBind(

1.  [Stream](../stream-class)\<T\> bind(
    1.  [Stream](../stream-class)\<S\>

    )

)
:::

Creates a [StreamTransformer](../streamtransformer-class) based on a
`bind` callback.

The returned stream transformer uses the `bind` argument to implement
the [StreamTransformer.bind](bind) API and can be used when the
transformation is available as a stream-to-stream function.

``` {.language-dart data-language="dart"}
final splitDecoded = StreamTransformer<List<int>, String>.fromBind(
    (stream) => stream.transform(utf8.decoder).transform(LineSplitter()));
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Since("2.1")
factory StreamTransformer.fromBind(Stream<T> Function(Stream<S>) bind) =
    _StreamBindTransformer<S, T>;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamTransformer/StreamTransformer.fromBind.html>
:::

[dart:async](../../dart-async/dart-async-library){._links-link}

castFrom\<SS, ST, TS, TT\> method
=================================

::: {.section .multi-line-signature}
[StreamTransformer](../streamtransformer-class)\<TS, TT\> castFrom\<SS,
ST, TS, TT\>(

1.  [StreamTransformer](../streamtransformer-class)\<SS, ST\> source

)
:::

Adapts `source` to be a `StreamTransformer<TS, TT>`.

This allows `source` to be used at the new type, but at run-time it must
satisfy the requirements of both the new type and its original type.

Data events passed into the returned transformer must also be instances
of `SS`, and data events produced by `source` for those events must also
be instances of `TT`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static StreamTransformer<TS, TT> castFrom<SS, ST, TS, TT>(
    StreamTransformer<SS, ST> source) {
  return new CastStreamTransformer<SS, ST, TS, TT>(source);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamTransformer/castFrom.html>
:::

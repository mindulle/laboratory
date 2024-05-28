[dart:async](../../dart-async/dart-async-library){._links-link}

cast\<RS, RT\> method
=====================

::: {.section .multi-line-signature}
[StreamTransformer](../streamtransformer-class)\<RS, RT\> cast\<RS,
RT\>()

::: {.features}
override
:::
:::

Provides a `StreamTransformer<RS, RT>` view of this stream transformer.

The resulting transformer will check at run-time that all data events of
the stream it transforms are actually instances of `S`, and it will
check that all data events produced by this transformer are actually
instances of `RT`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
StreamTransformer<RS, RT> cast<RS, RT>() =>
    StreamTransformer.castFrom<S, T, RS, RT>(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamTransformerBase/cast.html>
:::

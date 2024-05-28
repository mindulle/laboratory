[dart:async](../../dart-async/dart-async-library){._links-link}

castFrom\<S, T\> method
=======================

::: {.section .multi-line-signature}
[Stream](../stream-class)\<T\> castFrom\<S, T\>(

1.  [Stream](../stream-class)\<S\> source

)
:::

Adapts `source` to be a `Stream<T>`.

This allows `source` to be used at the new type, but at run-time it must
satisfy the requirements of both the new type and its original type.

Data events created by the source stream must also be instances of `T`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Stream<T> castFrom<S, T>(Stream<S> source) =>
    new CastStream<S, T>(source);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/castFrom.html>
:::

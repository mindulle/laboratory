[dart:async](../../dart-async/dart-async-library){._links-link}

cast\<R\> method
================

::: {.section .multi-line-signature}
[Stream](../stream-class)\<R\> cast\<R\>()
:::

Adapt this stream to be a `Stream<R>`.

This stream is wrapped as a `Stream<R>` which checks at run-time that
each data event emitted by this stream is also an instance of `R`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<R> cast<R>() => Stream.castFrom<T, R>(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/cast.html>
:::

[dart:async](../../dart-async/dart-async-library){._links-link}

StreamIterator\<T\> constructor
===============================

::: {.section .multi-line-signature}
StreamIterator\<T\>(

1.  [Stream](../stream-class)\<T\> stream

)
:::

Create a [StreamIterator](../streamiterator-class) on `stream`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory StreamIterator(Stream<T> stream) =>
    // TODO(lrn): use redirecting factory constructor when type
    // arguments are supported.
    new _StreamIterator<T>(stream);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamIterator/StreamIterator.html>
:::

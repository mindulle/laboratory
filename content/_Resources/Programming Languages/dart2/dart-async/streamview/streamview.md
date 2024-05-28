[dart:async](../../dart-async/dart-async-library){._links-link}

StreamView\<T\> constructor
===========================

::: {.section .multi-line-signature}
const StreamView\<T\>(

1.  [Stream](../stream-class)\<T\> stream

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const StreamView(Stream<T> stream)
    : _stream = stream,
      super._internal();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamView/StreamView.html>
:::

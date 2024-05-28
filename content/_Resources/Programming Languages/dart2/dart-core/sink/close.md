[dart:core](../../dart-core/dart-core-library){._links-link}

close method
============

::: {.section .multi-line-signature}
void close()
:::

Closes the sink.

The [add](add) method must not be called after this method.

Calling this method more than once is allowed, but does nothing.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void close();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Sink/close.html>
:::

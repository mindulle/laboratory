[dart:async](../../dart-async/dart-async-library){._links-link}

close method
============

::: {.section .multi-line-signature}
void close()

::: {.features}
override
:::
:::

Closes the sink.

Calling this method more than once is allowed, but does nothing.

Neither [add](add) nor [addError](adderror) must be called after this
method.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void close();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/EventSink/close.html>
:::

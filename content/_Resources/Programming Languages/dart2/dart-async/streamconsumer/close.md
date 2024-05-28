[dart:async](../../dart-async/dart-async-library){._links-link}

close method
============

::: {.section .multi-line-signature}
[Future](../future-class) close()
:::

Tells the consumer that no further streams will be added.

This allows the consumer to complete any remaining work and release
resources that are no longer needed

Returns a future which is completed when the consumer has shut down. If
cleaning up can fail, the error may be reported in the returned future,
otherwise it completes with `null`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future close();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamConsumer/close.html>
:::

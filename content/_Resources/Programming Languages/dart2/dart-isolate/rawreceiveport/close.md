[dart:isolate](../../dart-isolate/dart-isolate-library){._links-link}

close method
============

::: {.section .multi-line-signature}
void close()
:::

Closes the port.

After a call to this method, any incoming message is silently dropped.
The [handler](handler) will never be called again.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void close();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-isolate/RawReceivePort/close.html>
:::

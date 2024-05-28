[dart:io](../../dart-io/dart-io-library){._links-link}

destroy method
==============

::: {.section .multi-line-signature}
void destroy()
:::

Destroys the socket in both directions.

Calling [destroy](destroy) will make the send a close event on the
stream and will no longer react on data being piped to it.

Call [close](close) (inherited from [IOSink](../iosink-class)) to only
close the [Socket](../socket-class) for sending data.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void destroy();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Socket/destroy.html>
:::

[dart:io](../../dart-io/dart-io-library){._links-link}

closeSync method
================

::: {.section .multi-line-signature}
void closeSync()
:::

Closes the [RawSynchronousSocket](../rawsynchronoussocket-class).

Once [closeSync](closesync) has been called, attempting to call
[readSync](readsync), [readIntoSync](readintosync),
[writeFromSync](writefromsync), [remoteAddress](remoteaddress), and
[remotePort](remoteport) will cause a
[SocketException](../socketexception-class) to be thrown.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void closeSync();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawSynchronousSocket/closeSync.html>
:::

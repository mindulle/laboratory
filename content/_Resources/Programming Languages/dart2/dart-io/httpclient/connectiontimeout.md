[dart:io](../../dart-io/dart-io-library){._links-link}

connectionTimeout property
==========================

::: {.section .multi-line-signature}
[Duration](../../dart-core/duration-class)? connectionTimeout

::: {.features}
read / write
:::
:::

Gets and sets the connection timeout.

When connecting to a new host exceeds this timeout, a
[SocketException](../socketexception-class) is thrown. The timeout
applies only to connections initiated after the timeout is set.

When this is `null`, the OS default timeout is used. The default is
`null`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Duration? connectionTimeout;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClient/connectionTimeout.html>
:::

[dart:io](../../dart-io/dart-io-library){._links-link}

idleTimeout property
====================

::: {.section .multi-line-signature}
[Duration](../../dart-core/duration-class) idleTimeout

::: {.features}
read / write
:::
:::

Gets and sets the idle timeout of non-active persistent (keep-alive)
connections.

The default value is 15 seconds.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Duration idleTimeout = const Duration(seconds: 15);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClient/idleTimeout.html>
:::

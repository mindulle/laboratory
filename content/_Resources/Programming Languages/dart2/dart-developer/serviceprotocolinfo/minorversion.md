[dart:developer](../../dart-developer/dart-developer-library){._links-link}

minorVersion property
=====================

::: {.section .multi-line-signature}
[int](../../dart-core/int-class) minorVersion

::: {.features}
final
:::
:::

The minor version of the protocol. If the running Dart environment does
not support the service protocol, this is 0.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
final int minorVersion = _getServiceMinorVersion();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/ServiceProtocolInfo/minorVersion.html>
:::

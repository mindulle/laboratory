[dart:core](../../dart-core/dart-core-library){._links-link}

hasPort property
================

::: {#getter .section .multi-line-signature}
[bool](../bool-class) hasPort
:::

Whether the URI has an explicit port.

If the port number is the default port number (zero for unrecognized
schemes, with http (80) and https (443) being recognized), then the port
is made implicit and omitted from the URI.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool get hasPort;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Uri/hasPort.html>
:::

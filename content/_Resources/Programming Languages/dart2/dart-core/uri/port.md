[dart:core](../../dart-core/dart-core-library){._links-link}

port property
=============

::: {#getter .section .multi-line-signature}
[int](../int-class) port
:::

The port part of the authority component.

The value is the default port if there is no port number in the
authority component. That\'s 80 for http, 443 for https, and 0 for
everything else.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get port;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Uri/port.html>
:::

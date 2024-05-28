[dart:io](../../dart-io/dart-io-library){._links-link}

closing property
================

::: {.section .multi-line-signature}
[int](../../dart-core/int-class) closing

::: {.features}
read / write
:::
:::

Number of connections which are preparing to close.

Note: These connections are also part of the [active](active) count as
they might still be sending data to the client before finally closing.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int closing = 0;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpConnectionsInfo/closing.html>
:::

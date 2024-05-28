[dart:io](../../dart-io/dart-io-library){._links-link}

add method
==========

::: {.section .multi-line-signature}
void add(

1.  dynamic data

)

::: {.features}
override
:::
:::

Sends data on the WebSocket connection. The data in `data` must be
either a `String`, or a `List<int>` holding bytes.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void add(/*String|List<int>*/ data);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/WebSocket/add.html>
:::

[dart:io](../../dart-io/dart-io-library){._links-link}

addUtf8Text method
==================

::: {.section .multi-line-signature}
void addUtf8Text(

1.  [List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>
    bytes

)
:::

Sends a text message with the text represented by `bytes`.

The `bytes` should be valid UTF-8 encoded Unicode characters. If they
are not, the receiving end will close the connection.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void addUtf8Text(List<int> bytes);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/WebSocket/addUtf8Text.html>
:::

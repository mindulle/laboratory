[dart:io](../../dart-io/dart-io-library){._links-link}

compressionDefault constant
===========================

::: {.section .multi-line-signature}
[CompressionOptions](../compressionoptions-class) const
compressionDefault
:::

Default [WebSocket](../websocket-class) compression configuration.

Enables compression with default window sizes and no reuse. This is the
default options used by [WebSocket.connect](../websocket/connect) if no
[CompressionOptions](../compressionoptions-class) is supplied.

-   `clientNoContextTakeover`: false
-   `serverNoContextTakeover`: false
-   `clientMaxWindowBits`: null (default maximal window size of 15 bits)
-   `serverMaxWindowBits`: null (default maximal window size of 15 bits)

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const CompressionOptions compressionDefault = CompressionOptions();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/CompressionOptions/compressionDefault-constant.html>
:::

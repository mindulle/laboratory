[dart:io](../../dart-io/dart-io-library){._links-link}

addStream method
================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) addStream(

1.  [Stream](../../dart-async/stream-class) stream

)

::: {.features}
override
:::
:::

Sends data from a stream on WebSocket connection. Each data event from
`stream` will be send as a single WebSocket frame. The data from
`stream` must be either `String`s, or `List<int>`s holding bytes.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future addStream(Stream stream);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/WebSocket/addStream.html>
:::

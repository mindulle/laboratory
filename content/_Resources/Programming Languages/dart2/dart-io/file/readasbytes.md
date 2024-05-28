[dart:io](../../dart-io/dart-io-library){._links-link}

readAsBytes method
==================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[Uint8List](../../dart-typed_data/uint8list-class)\>
readAsBytes()
:::

Reads the entire file contents as a list of bytes.

Returns a `Future<Uint8List>` that completes with the list of bytes that
is the contents of the file.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<Uint8List> readAsBytes();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/File/readAsBytes.html>
:::

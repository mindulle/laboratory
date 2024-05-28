[dart:io](../../dart-io/dart-io-library){._links-link}

readAsString method
===================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[String](../../dart-core/string-class)\>
readAsString(

1.  {[Encoding](../../dart-convert/encoding-class) encoding = utf8}

)
:::

Reads the entire file contents as a string using the given
[Encoding](../../dart-convert/encoding-class).

Returns a `Future<String>` that completes with the string once the file
contents has been read.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<String> readAsString({Encoding encoding = utf8});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/File/readAsString.html>
:::

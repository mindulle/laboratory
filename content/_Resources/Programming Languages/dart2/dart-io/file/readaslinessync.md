[dart:io](../../dart-io/dart-io-library){._links-link}

readAsLinesSync method
======================

::: {.section .multi-line-signature}
[List](../../dart-core/list-class)\<[String](../../dart-core/string-class)\>
readAsLinesSync(

1.  {[Encoding](../../dart-convert/encoding-class) encoding = utf8}

)
:::

Synchronously reads the entire file contents as lines of text using the
given [Encoding](../../dart-convert/encoding-class).

Throws a [FileSystemException](../filesystemexception-class) if the
operation fails.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
List<String> readAsLinesSync({Encoding encoding = utf8});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/File/readAsLinesSync.html>
:::

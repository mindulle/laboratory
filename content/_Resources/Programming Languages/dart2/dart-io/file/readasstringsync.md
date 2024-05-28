[dart:io](../../dart-io/dart-io-library){._links-link}

readAsStringSync method
=======================

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) readAsStringSync(

1.  {[Encoding](../../dart-convert/encoding-class) encoding = utf8}

)
:::

Synchronously reads the entire file contents as a string using the given
[Encoding](../../dart-convert/encoding-class).

Throws a [FileSystemException](../filesystemexception-class) if the
operation fails.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String readAsStringSync({Encoding encoding = utf8});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/File/readAsStringSync.html>
:::

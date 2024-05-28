[dart:io](../../dart-io/dart-io-library){._links-link}

stat method
===========

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[FileStat](../filestat-class)\>
stat(

1.  [String](../../dart-core/string-class) path

)
:::

Asynchronously returns `FileStat` information for `path`.

When this override is installed, this function overrides the behavior of
`FileStat.stat()`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<FileStat> stat(String path) {
  return FileStat._stat(path);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/IOOverrides/stat.html>
:::

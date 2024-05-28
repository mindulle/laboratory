[dart:io](../../dart-io/dart-io-library){._links-link}

statSync method
===============

::: {.section .multi-line-signature}
[FileStat](../filestat-class) statSync(

1.  [String](../../dart-core/string-class) path

)
:::

Returns [FileStat](../filestat-class) information for `path`.

When this override is installed, this function overrides the behavior of
`FileStat.statSync()`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
FileStat statSync(String path) {
  return FileStat._statSyncInternal(path);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/IOOverrides/statSync.html>
:::

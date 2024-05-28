[dart:io](../../dart-io/dart-io-library){._links-link}

stat method
===========

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[FileStat](../filestat-class)\>
stat(

1.  [String](../../dart-core/string-class) path

)
:::

Asynchronously calls the operating system\'s `stat()` function (or
equivalent) on `path`.

If `path` is a symbolic link then it is resolved and results for the
resulting file are returned.

Returns a [Future](../../dart-async/future-class) which completes with
the same results as [statSync](statsync).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Future<FileStat> stat(String path) {
  final IOOverrides? overrides = IOOverrides.current;
  if (overrides == null) {
    return _stat(path);
  }
  return overrides.stat(path);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/FileStat/stat.html>
:::

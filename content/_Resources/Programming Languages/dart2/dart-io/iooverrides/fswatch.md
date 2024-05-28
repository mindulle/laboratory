[dart:io](../../dart-io/dart-io-library){._links-link}

fsWatch method
==============

::: {.section .multi-line-signature}
[Stream](../../dart-async/stream-class)\<[FileSystemEvent](../filesystemevent-class)\>
fsWatch(

1.  [String](../../dart-core/string-class) path,
2.  [int](../../dart-core/int-class) events,
3.  [bool](../../dart-core/bool-class) recursive

)
:::

Returns a [Stream](../../dart-async/stream-class) of `FileSystemEvent`s.

When this override is installed, this function overrides the behavior of
`FileSystemEntity.watch()`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<FileSystemEvent> fsWatch(String path, int events, bool recursive) {
  return _FileSystemWatcher._watch(path, events, recursive);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/IOOverrides/fsWatch.html>
:::

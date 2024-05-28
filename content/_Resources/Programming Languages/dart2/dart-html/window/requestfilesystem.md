[dart:html](../../dart-html/dart-html-library){._links-link}

requestFileSystem method
========================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[FileSystem](../filesystem-class)\>
requestFileSystem(

1.  [int](../../dart-core/int-class) size,
2.  {[bool](../../dart-core/bool-class) persistent = false}

)
:::

Access a sandboxed file system of `size` bytes.

If `persistent` is true, the application will request permission from
the user to create lasting storage. This storage cannot be freed without
the user\'s permission. Returns a
[Future](../../dart-async/future-class) whose value stores a reference
to the sandboxed file system for use. Because the file system is
sandboxed, applications cannot access file systems created in other web
pages.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<FileSystem> requestFileSystem(int size, {bool persistent: false}) {
  return _requestFileSystem(persistent ? 1 : 0, size);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Window/requestFileSystem.html>
:::

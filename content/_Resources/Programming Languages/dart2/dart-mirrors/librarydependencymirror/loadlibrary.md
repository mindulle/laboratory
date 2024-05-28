[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

loadLibrary method
==================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[LibraryMirror](../librarymirror-class)\>
loadLibrary()
:::

Returns a future that completes with a library mirror on the library
being imported or exported when it is loaded, and initiates a load of
that library if it is not loaded.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<LibraryMirror> loadLibrary();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/LibraryDependencyMirror/loadLibrary.html>
:::

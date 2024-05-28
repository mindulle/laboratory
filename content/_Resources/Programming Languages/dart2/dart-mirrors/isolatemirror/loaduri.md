[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

loadUri method
==============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[LibraryMirror](../librarymirror-class)\>
loadUri(

1.  [Uri](../../dart-core/uri-class) uri

)
:::

Loads the library at the given uri into this isolate.

WARNING: You are strongly encouraged to use Isolate.spawnUri instead
when possible. IsolateMirror.loadUri should only be used when
synchronous communication or shared state with dynamically loaded code
is needed.

If a library with the same canonicalized uri has already been loaded,
the existing library will be returned. (The isolate will not load a new
copy of the library.)

This behavior is similar to the behavior of an import statement that
appears in the root library, except that the import scope of the root
library is not changed.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<LibraryMirror> loadUri(Uri uri);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/IsolateMirror/loadUri.html>
:::

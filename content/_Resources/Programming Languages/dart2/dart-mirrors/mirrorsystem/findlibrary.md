[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

findLibrary method
==================

::: {.section .multi-line-signature}
[LibraryMirror](../librarymirror-class) findLibrary(

1.  [Symbol](../../dart-core/symbol-class) libraryName

)
:::

Returns the unique library named `libraryName` if it exists.

If no unique library exists, an error is thrown.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external LibraryMirror findLibrary(Symbol libraryName);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/MirrorSystem/findLibrary.html>
:::

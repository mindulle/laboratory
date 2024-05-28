[dart:io](../../dart-io/dart-io-library){._links-link}

createSync method
=================

::: {.section .multi-line-signature}
void createSync(

1.  {[bool](../../dart-core/bool-class) recursive = false}

)
:::

Synchronously creates the directory if it doesn\'t exist.

If `recursive` is false, only the last directory in the path is created.
If `recursive` is true, all non-existing path components are created. If
the directory already exists nothing is done.

If the directory cannot be created an exception is thrown.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void createSync({bool recursive = false});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Directory/createSync.html>
:::

[dart:io](../../dart-io/dart-io-library){._links-link}

create method
=============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[Directory](../directory-class)\>
create(

1.  {[bool](../../dart-core/bool-class) recursive = false}

)
:::

Creates the directory if it doesn\'t exist.

If `recursive` is false, only the last directory in the path is created.
If `recursive` is true, all non-existing path components are created. If
the directory already exists nothing is done.

Returns a `Future<Directory>` that completes with this directory once it
has been created. If the directory cannot be created the future
completes with an exception.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<Directory> create({bool recursive = false});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Directory/create.html>
:::

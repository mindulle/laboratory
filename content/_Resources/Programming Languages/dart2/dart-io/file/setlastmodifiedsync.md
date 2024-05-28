[dart:io](../../dart-io/dart-io-library){._links-link}

setLastModifiedSync method
==========================

::: {.section .multi-line-signature}
void setLastModifiedSync(

1.  [DateTime](../../dart-core/datetime-class) time

)
:::

Synchronously modifies the time the file was last modified.

If the attributes cannot be set, throws a
[FileSystemException](../filesystemexception-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void setLastModifiedSync(DateTime time);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/File/setLastModifiedSync.html>
:::

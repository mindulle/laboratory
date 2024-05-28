[dart:io](../../dart-io/dart-io-library){._links-link}

setLastAccessedSync method
==========================

::: {.section .multi-line-signature}
void setLastAccessedSync(

1.  [DateTime](../../dart-core/datetime-class) time

)
:::

Synchronously modifies the time the file was last accessed.

Throws a [FileSystemException](../filesystemexception-class) if the time
cannot be set.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void setLastAccessedSync(DateTime time);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/File/setLastAccessedSync.html>
:::

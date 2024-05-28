[dart:io](../../dart-io/dart-io-library){._links-link}

lastAccessedSync method
=======================

::: {.section .multi-line-signature}
[DateTime](../../dart-core/datetime-class) lastAccessedSync()
:::

The last-accessed time of the file.

Returns the date and time when the file was last accessed, if the
information is available. Blocks until the information can be returned
or it is determined that the information is not available.

Throws a [FileSystemException](../filesystemexception-class) if the
operation fails.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
DateTime lastAccessedSync();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/File/lastAccessedSync.html>
:::

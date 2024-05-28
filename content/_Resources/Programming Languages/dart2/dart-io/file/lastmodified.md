[dart:io](../../dart-io/dart-io-library){._links-link}

lastModified method
===================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[DateTime](../../dart-core/datetime-class)\>
lastModified()
:::

Get the last-modified time of the file.

Returns a `Future<DateTime>` that completes with the date and time when
the file was last modified, if the information is available.

Throws a [FileSystemException](../filesystemexception-class) if the
operation fails.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<DateTime> lastModified();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/File/lastModified.html>
:::

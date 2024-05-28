[dart:io](../../dart-io/dart-io-library){._links-link}

setLastModified method
======================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) setLastModified(

1.  [DateTime](../../dart-core/datetime-class) time

)
:::

Modifies the time the file was last modified.

Returns a [Future](../../dart-async/future-class) that completes once
the operation has completed.

Throws a [FileSystemException](../filesystemexception-class) if the time
cannot be set.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future setLastModified(DateTime time);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/File/setLastModified.html>
:::

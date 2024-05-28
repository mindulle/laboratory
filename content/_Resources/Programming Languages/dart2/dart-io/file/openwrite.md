[dart:io](../../dart-io/dart-io-library){._links-link}

openWrite method
================

::: {.section .multi-line-signature}
[IOSink](../iosink-class) openWrite(

1.  {[FileMode](../filemode-class) mode = FileMode.write,
2.  [Encoding](../../dart-convert/encoding-class) encoding = utf8}

)
:::

Creates a new independent [IOSink](../iosink-class) for the file.

The [IOSink](../iosink-class) must be closed when no longer used, to
free system resources.

An [IOSink](../iosink-class) for a file can be opened in two modes:

-   [FileMode.write](../filemode/write-constant): truncates the file to
    length zero.
-   [FileMode.append](../filemode/append-constant): sets the initial
    write position to the end of the file.

When writing strings through the returned [IOSink](../iosink-class) the
encoding specified using `encoding` will be used. The returned
[IOSink](../iosink-class) has an `encoding` property which can be
changed after the [IOSink](../iosink-class) has been created.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
IOSink openWrite({FileMode mode = FileMode.write, Encoding encoding = utf8});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/File/openWrite.html>
:::

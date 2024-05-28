[dart:io](../../dart-io/dart-io-library){._links-link}

target method
=============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[String](../../dart-core/string-class)\>
target()
:::

Gets the target of the link.

Returns a future that completes with the path to the target.

If the returned target is a relative path, it is relative to the
directory containing the link.

If the link does not exist, or is not a link, the future completes with
a [FileSystemException](../filesystemexception-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<String> target();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Link/target.html>
:::

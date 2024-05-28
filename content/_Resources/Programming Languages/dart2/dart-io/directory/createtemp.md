[dart:io](../../dart-io/dart-io-library){._links-link}

createTemp method
=================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[Directory](../directory-class)\>
createTemp(

1.  \[[String](../../dart-core/string-class)? prefix\]

)
:::

Creates a temporary directory in this directory.

Additional random characters are appended to `prefix` to produce a
unique directory name. If `prefix` is missing or null, the empty string
is used as `prefix`.

Returns a `Future<Directory>` that completes with the newly created
temporary directory.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<Directory> createTemp([String? prefix]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Directory/createTemp.html>
:::

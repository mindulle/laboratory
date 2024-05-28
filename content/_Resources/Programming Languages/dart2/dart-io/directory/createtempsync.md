[dart:io](../../dart-io/dart-io-library){._links-link}

createTempSync method
=====================

::: {.section .multi-line-signature}
[Directory](../directory-class) createTempSync(

1.  \[[String](../../dart-core/string-class)? prefix\]

)
:::

Synchronously creates a temporary directory in this directory.

Additional random characters are appended to `prefix` to produce a
unique directory name. If `prefix` is missing or null, the empty string
is used as `prefix`.

Returns the newly created temporary directory.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Directory createTempSync([String? prefix]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Directory/createTempSync.html>
:::

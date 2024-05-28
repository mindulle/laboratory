[dart:io](../../dart-io/dart-io-library){._links-link}

getSystemTempDirectory method
=============================

::: {.section .multi-line-signature}
[Directory](../directory-class) getSystemTempDirectory()
:::

Returns the system temporary directory.

When this override is installed, this function overrides the behavior of
`Directory.systemTemp`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Directory getSystemTempDirectory() => _Directory.systemTemp;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/IOOverrides/getSystemTempDirectory.html>
:::

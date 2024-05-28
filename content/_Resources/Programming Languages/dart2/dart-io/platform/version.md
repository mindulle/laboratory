[dart:io](../../dart-io/dart-io-library){._links-link}

version property
================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) version
:::

The version of the current Dart runtime.

The value is a [semantic versioning](http://semver.org) string
representing the version of the current Dart runtime, possibly followed
by whitespace and other version and build details.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static String get version => _version;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Platform/version.html>
:::

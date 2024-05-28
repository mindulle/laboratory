[dart:io](../../dart-io/dart-io-library){._links-link}

packageConfig property
======================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class)? packageConfig
:::

The `--packages` flag passed to the executable used to run the script in
this isolate.

If present, it specifies a file describing how Dart packages are looked
up.

Is `null` if there is no `--packages` flag.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static String? get packageConfig => _Platform.packageConfig;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Platform/packageConfig.html>
:::

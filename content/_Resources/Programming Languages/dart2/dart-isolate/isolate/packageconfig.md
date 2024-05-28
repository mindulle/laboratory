[dart:isolate](../../dart-isolate/dart-isolate-library){._links-link}

packageConfig property
======================

::: {#getter .section .multi-line-signature}
[Future](../../dart-async/future-class)\<[Uri](../../dart-core/uri-class)?\>
packageConfig
:::

The location of the package configuration of the current isolate, if
any.

If the isolate has not been setup for package resolution, this location
is `null`, otherwise it is a URI referencing the package config file.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external static Future<Uri?> get packageConfig;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-isolate/Isolate/packageConfig.html>
:::

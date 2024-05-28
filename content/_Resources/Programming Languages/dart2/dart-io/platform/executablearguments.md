[dart:io](../../dart-io/dart-io-library){._links-link}

executableArguments property
============================

::: {#getter .section .multi-line-signature}
[List](../../dart-core/list-class)\<[String](../../dart-core/string-class)\>
executableArguments
:::

The flags passed to the executable used to run the script in this
isolate.

These are the command-line flags to the executable that precedes the
script name. Provides a new list every time the value is read.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static List<String> get executableArguments => _Platform.executableArguments;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Platform/executableArguments.html>
:::

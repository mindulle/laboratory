[dart:io](../../dart-io/dart-io-library){._links-link}

resolvedExecutable property
===========================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) resolvedExecutable
:::

The path of the executable used to run the script in this isolate after
it has been resolved by the OS.

This is the absolute path, with all symlinks resolved, to the executable
used to run the script.

See [executable](executable) for the unresolved version.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static String get resolvedExecutable => _Platform.resolvedExecutable;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Platform/resolvedExecutable.html>
:::

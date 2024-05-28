[dart:io](../../dart-io/dart-io-library){._links-link}

absolute property
=================

::: {#getter .section .multi-line-signature}
[File](../file-class) absolute

::: {.features}
override
:::
:::

A [File](../file-class) with the absolute path of [path](path).

The absolute path is computed by prefixing a relative path with the
current working directory, or returning an absolute path unchanged.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
File get absolute;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/File/absolute.html>
:::

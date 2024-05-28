[dart:io](../../dart-io/dart-io-library){._links-link}

getCurrentDirectory method
==========================

::: {.section .multi-line-signature}
[Directory](../directory-class) getCurrentDirectory()
:::

Returns the current working directory.

When this override is installed, this function overrides the behavior of
the static getter `Directory.current`

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Directory getCurrentDirectory() => _Directory.current;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/IOOverrides/getCurrentDirectory.html>
:::

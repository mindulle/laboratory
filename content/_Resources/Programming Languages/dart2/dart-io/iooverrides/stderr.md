[dart:io](../../dart-io/dart-io-library){._links-link}

stderr property
===============

::: {#getter .section .multi-line-signature}
[Stdout](../stdout-class) stderr
:::

The standard output stream of errors written by this program.

When this override is installed, this getter overrides the behavior of
the top-level `stderr` getter.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stdout get stderr {
  return _stderr;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/IOOverrides/stderr.html>
:::

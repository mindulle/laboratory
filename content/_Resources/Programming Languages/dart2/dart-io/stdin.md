[dart:io](../dart-io/dart-io-library){._links-link}

stdin top-level property
========================

::: {#getter .section .multi-line-signature}
[Stdin](stdin-class) stdin
:::

The standard input stream of data read by this program.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stdin get stdin {
  return IOOverrides.current?.stdin ?? _stdin;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/stdin.html>
:::

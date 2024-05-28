[dart:io](../../dart-io/dart-io-library){._links-link}

terminalColumns property
========================

::: {#getter .section .multi-line-signature}
[int](../../dart-core/int-class) terminalColumns
:::

The number of columns of the terminal.

If no terminal is attached to stdout, a
[StdoutException](../stdoutexception-class) is thrown. See
[hasTerminal](hasterminal) for more info.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get terminalColumns => _terminalColumns(_fd);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Stdout/terminalColumns.html>
:::

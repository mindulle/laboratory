[dart:io](../../dart-io/dart-io-library){._links-link}

lineMode property
=================

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class) lineMode
:::

Whether line mode is enabled on [stdin](../stdin).

If enabled, characters are delayed until a newline character is entered.
If disabled, characters will be available as typed.

Default depends on the parent process, but is usually enabled.

On POSIX systems this mode is the `icanon` local terminal mode.

On Windows this mode can only be disabled if [echoMode](echomode) is
disabled as well.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external bool get lineMode;
```

::: {#setter .section .multi-line-signature}
void lineMode=([bool](../../dart-core/bool-class) lineMode)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external set lineMode(bool lineMode);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Stdin/lineMode.html>
:::

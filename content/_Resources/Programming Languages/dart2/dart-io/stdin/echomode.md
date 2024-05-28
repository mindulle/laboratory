[dart:io](../../dart-io/dart-io-library){._links-link}

echoMode property
=================

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class) echoMode
:::

Whether echo mode is enabled on [stdin](../stdin).

If disabled, input from the console will not be echoed.

Default depends on the parent process, but is usually enabled.

On POSIX systems this mode is the `echo` local terminal mode. Before
Dart 2.18, it also controlled the `echonl` mode, which is now controlled
by [echoNewlineMode](echonewlinemode).

On Windows this mode can only be enabled if [lineMode](linemode) is
enabled as well.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external bool get echoMode;
```

::: {#setter .section .multi-line-signature}
void echoMode=([bool](../../dart-core/bool-class) echoMode)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external set echoMode(bool echoMode);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Stdin/echoMode.html>
:::

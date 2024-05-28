[dart:io](../../dart-io/dart-io-library){._links-link}

supportsAnsiEscapes property
============================

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class) supportsAnsiEscapes
:::

Whether connected to a terminal that supports ANSI escape sequences.

Not all terminals are recognized, and not all recognized terminals can
report whether they support ANSI escape sequences, so this value is a
best-effort attempt at detecting the support.

The actual escape sequence support may differ between terminals, with
some terminals supporting more escape sequences than others, and some
terminals even differing in behavior for the same escape sequence.

The ANSI color selection is generally supported.

Currently, a `TERM` environment variable containing the string `xterm`
will be taken as evidence that ANSI escape sequences are supported. On
Windows, only versions of Windows 10 after v.1511 (\"TH2\", OS build
10586) will be detected as supporting the output of ANSI escape
sequences, and only versions after v.1607 (\"Anniversary Update\", OS
build 14393) will be detected as supporting the input of ANSI escape
sequences.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external bool get supportsAnsiEscapes;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Stdin/supportsAnsiEscapes.html>
:::

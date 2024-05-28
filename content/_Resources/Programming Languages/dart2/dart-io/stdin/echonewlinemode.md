[dart:io](../../dart-io/dart-io-library){._links-link}

echoNewlineMode property
========================

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class) echoNewlineMode

::: {.features}
\@Since(\"2.18\")
:::
:::

Whether echo newline mode is enabled on [stdin](../stdin).

If enabled, newlines from the terminal will be echoed even if the
regular [echoMode](echomode) is disabled. This mode may require
`lineMode` to be turned on to have an effect.

Default depends on the parent process, but is usually disabled.

On POSIX systems this mode is the `echonl` local terminal mode.

On Windows this mode cannot be set.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Since("2.18")
external bool get echoNewlineMode;
```

::: {#setter .section .multi-line-signature}
void echoNewlineMode=([bool](../../dart-core/bool-class)
echoNewlineMode)

::: {.features}
\@Since(\"2.18\")
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Since("2.18")
external set echoNewlineMode(bool echoNewlineMode);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Stdin/echoNewlineMode.html>
:::

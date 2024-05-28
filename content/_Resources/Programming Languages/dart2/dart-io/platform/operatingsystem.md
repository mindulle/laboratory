[dart:io](../../dart-io/dart-io-library){._links-link}

operatingSystem property
========================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) operatingSystem
:::

A string representing the operating system or platform.

Possible values include: \"android\" \"fuchsia\" \"ios\" \"linux\"
\"macos\" \"windows\"

Note that this list may change over time so platform-specific logic
should be guarded by the appropriate boolean getter e.g.
[isMacOS](ismacos).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static String get operatingSystem => _operatingSystem;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Platform/operatingSystem.html>
:::

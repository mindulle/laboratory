[dart:core](../../dart-core/dart-core-library){._links-link}

base property
=============

::: {#getter .section .multi-line-signature}
[Uri](../uri-class) base
:::

The natural base URI for the current platform.

When running in a browser, this is the current URL of the current page
(from `window.location.href`).

When not running in a browser, this is the file URI referencing the
current working directory.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external static Uri get base;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Uri/base.html>
:::

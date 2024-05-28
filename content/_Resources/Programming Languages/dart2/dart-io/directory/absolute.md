[dart:io](../../dart-io/dart-io-library){._links-link}

absolute property
=================

::: {#getter .section .multi-line-signature}
[Directory](../directory-class) absolute

::: {.features}
override
:::
:::

A [Directory](../directory-class) whose path is the absolute path of
[this](../directory-class).

The absolute path is computed by prefixing a relative path with the
current working directory, or by returning an absolute path unchanged.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Directory get absolute;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Directory/absolute.html>
:::

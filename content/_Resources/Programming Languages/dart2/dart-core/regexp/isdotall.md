[dart:core](../../dart-core/dart-core-library){._links-link}

isDotAll property
=================

::: {#getter .section .multi-line-signature}
[bool](../bool-class) isDotAll

::: {.features}
\@Since(\"2.4\")
:::
:::

Whether \".\" in this regular expression matches line terminators.

When false, the \".\" character matches a single character, unless that
character is a line terminator. When true, then the \".\" character will
match any single character including line terminators.

This feature is distinct from [isMultiLine](ismultiline), as they affect
the behavior of different pattern characters, and so they can be used
together or separately.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Since("2.4")
bool get isDotAll;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/RegExp/isDotAll.html>
:::

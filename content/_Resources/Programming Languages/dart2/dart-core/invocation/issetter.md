[dart:core](../../dart-core/dart-core-library){._links-link}

isSetter property
=================

::: {#getter .section .multi-line-signature}
[bool](../bool-class) isSetter
:::

Whether the invocation was a setter call.

If so, [positionalArguments](positionalarguments) has exactly one
positional argument, [namedArguments](namedarguments) is empty, and
typeArguments is empty.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool get isSetter;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Invocation/isSetter.html>
:::

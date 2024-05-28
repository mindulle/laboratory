[dart:core](../../dart-core/dart-core-library){._links-link}

typeArguments property
======================

::: {#getter .section .multi-line-signature}
[List](../list-class)\<[Type](../type-class)\> typeArguments
:::

An unmodifiable view of the type arguments of the call.

If the member is a getter, setter or operator, the type argument list is
always empty.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
List<Type> get typeArguments => const <Type>[];
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Invocation/typeArguments.html>
:::

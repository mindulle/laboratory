[dart:core](../../dart-core/dart-core-library){._links-link}

operator == method
==================

::: {.section .multi-line-signature}
[bool](../bool-class) operator ==(

1.  [Object](../object-class) other

)

::: {.features}
override
:::
:::

Whether `other` is a [Type](../type-class) instance representing an
equivalent type.

The language specification dictates which types are considered to be the
equivalent. If two types are equivalent, it\'s guaranteed that they are
subtypes of each other, but there are also types which are subtypes of
each other, and which are not equivalent (for example `dynamic` and
`void`, or `FutureOr<Object>` and `Object`).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool operator ==(Object other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Type/operator_equals.html>
:::

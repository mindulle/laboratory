[dart:mirrors](../../dart-mirrors/dart-mirrors-library){._links-link}

operator == method
==================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) operator ==(

1.  [Object](../../dart-core/object-class) other

)

::: {.features}
override
:::
:::

Whether this mirror is equal to `other`.

The equality holds if and only if

1.  `other` is a mirror of the same kind, and
2.  This mirror and `other` reflect the same class.

Note that if the reflected class is an invocation of a generic class, 2.
implies that the reflected class and `other` have equal type arguments.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool operator ==(Object other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/ClassMirror/operator_equals.html>
:::

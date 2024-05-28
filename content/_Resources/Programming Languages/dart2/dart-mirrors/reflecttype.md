[dart:mirrors](../dart-mirrors/dart-mirrors-library){._links-link}

reflectType function
====================

::: {.section .multi-line-signature}
[TypeMirror](typemirror-class) reflectType(

1.  [Type](../dart-core/type-class) key,
2.  \[[List](../dart-core/list-class)\<[Type](../dart-core/type-class)\>?
    typeArguments\]

)
:::

Reflects the type represented by `key`.

If `key` is not an instance of [Type](../dart-core/type-class), then
this function throws an
[ArgumentError](../dart-core/argumenterror-class).

Optionally takes a list of `typeArguments` for generic classes. If the
list is provided, then the `key` must be a generic class type, and the
number of the provided type arguments must be equal to the number of
type variables declared by the class.

Note that since one cannot obtain a [Type](../dart-core/type-class)
object from another isolate, this function can only be used to obtain
type mirrors on types of the current isolate.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external TypeMirror reflectType(Type key, [List<Type>? typeArguments]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-mirrors/reflectType.html>
:::

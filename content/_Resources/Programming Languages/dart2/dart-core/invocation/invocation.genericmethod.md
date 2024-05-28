[dart:core](../../dart-core/dart-core-library){._links-link}

Invocation.genericMethod constructor
====================================

::: {.section .multi-line-signature}
Invocation.genericMethod(

1.  [Symbol](../symbol-class) memberName,
2.  [Iterable](../iterable-class)\<[Type](../type-class)\>?
    typeArguments,
3.  [Iterable](../iterable-class)\<[Object](../object-class)?\>?
    positionalArguments,
4.  \[[Map](../map-class)\<[Symbol](../symbol-class),
    [Object](../object-class)?\>? namedArguments\]

)
:::

Creates an invocation corresponding to a generic method invocation.

If `typeArguments` is `null` or empty, the constructor is equivalent to
calling [Invocation.method](invocation.method) with the remaining
arguments. All the individual type arguments must be non-null.

If the named arguments are omitted, they default to no named arguments.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Invocation.genericMethod(Symbol memberName,
        Iterable<Type>? typeArguments, Iterable<Object?>? positionalArguments,
        [Map<Symbol, Object?>? namedArguments]) =>
    _Invocation.method(
        memberName, typeArguments, positionalArguments, namedArguments);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Invocation/Invocation.genericMethod.html>
:::

[dart:core](../../dart-core/dart-core-library){._links-link}

Invocation.method constructor
=============================

::: {.section .multi-line-signature}
Invocation.method(

1.  [Symbol](../symbol-class) memberName,
2.  [Iterable](../iterable-class)\<[Object](../object-class)?\>?
    positionalArguments,
3.  \[[Map](../map-class)\<[Symbol](../symbol-class),
    [Object](../object-class)?\>? namedArguments\]

)
:::

Creates an invocation corresponding to a method invocation.

The method invocation has no type arguments. If the named arguments are
omitted, they default to no named arguments.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Invocation.method(
        Symbol memberName, Iterable<Object?>? positionalArguments,
        [Map<Symbol, Object?>? namedArguments]) =>
    _Invocation.method(memberName, null, positionalArguments, namedArguments);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Invocation/Invocation.method.html>
:::

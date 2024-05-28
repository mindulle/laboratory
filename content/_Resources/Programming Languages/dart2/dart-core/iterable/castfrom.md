[dart:core](../../dart-core/dart-core-library){._links-link}

castFrom\<S, T\> method
=======================

::: {.section .multi-line-signature}
[Iterable](../iterable-class)\<T\> castFrom\<S, T\>(

1.  [Iterable](../iterable-class)\<S\> source

)
:::

Adapts `source` to be an `Iterable<T>`.

Any time the iterable would produce an element that is not a `T`, the
element access will throw. If all elements of `source` are actually
instances of `T`, or if only elements that are actually instances of `T`
are accessed, then the resulting iterable can be used as an
`Iterable<T>`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Iterable<T> castFrom<S, T>(Iterable<S> source) =>
    CastIterable<S, T>(source);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Iterable/castFrom.html>
:::

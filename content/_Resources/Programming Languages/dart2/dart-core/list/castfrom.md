[dart:core](../../dart-core/dart-core-library){._links-link}

castFrom\<S, T\> method
=======================

::: {.section .multi-line-signature}
[List](../list-class)\<T\> castFrom\<S, T\>(

1.  [List](../list-class)\<S\> source

)

::: {.features}
override
:::
:::

Adapts `source` to be a `List<T>`.

Any time the list would produce an element that is not a `T`, the
element access will throw.

Any time a `T` value is attempted stored into the adapted list, the
store will throw unless the value is also an instance of `S`.

If all accessed elements of `source` are actually instances of `T`, and
if all elements stored into the returned list are actually instance of
`S`, then the returned list can be used as a `List<T>`.

Methods which accept `Object?` as argument, like
[contains](../iterable/contains) and [remove](remove), will pass the
argument directly to the this list\'s method without any checks.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static List<T> castFrom<S, T>(List<S> source) => CastList<S, T>(source);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/List/castFrom.html>
:::

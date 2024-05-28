[dart:core](../../dart-core/dart-core-library){._links-link}

whereType\<T\> method
=====================

::: {.section .multi-line-signature}
[Iterable](../iterable-class)\<T\> whereType\<T\>()
:::

Returns a new lazy [Iterable](../iterable-class) with all elements that
have type `T`.

The matching elements have the same order in the returned iterable as
they have in [iterator](iterator).

This method returns a view of the mapped elements. Iterating will not
cache results, and thus iterating multiple times over the returned
[Iterable](../iterable-class) may yield different results, if the
underlying elements change between iterations.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Iterable<T> whereType<T>() => WhereTypeIterable<T>(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Iterable/whereType.html>
:::

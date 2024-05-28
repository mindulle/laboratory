[dart:collection](../../dart-collection/dart-collection-library){._links-link}

cast\<R\> method
================

::: {.section .multi-line-signature}
[Set](../../dart-core/set-class)\<R\> cast\<R\>()

::: {.features}
override
:::
:::

Provides a view of this iterable as an iterable of `R` instances.

If this iterable only contains instances of `R`, all operations will
work correctly. If any operation tries to access an element that is not
an instance of `R`, the access will throw instead.

When the returned iterable creates a new object that depends on the type
`R`, e.g., from [toList](../setmixin/tolist), it will have exactly the
type `R`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Set<R> cast<R>() => Set.castFrom<E, R>(this, newSet: _newSet);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SplayTreeSet/cast.html>
:::

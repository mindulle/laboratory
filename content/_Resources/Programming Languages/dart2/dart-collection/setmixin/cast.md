[dart:collection](../../dart-collection/dart-collection-library){._links-link}

cast\<R\> method
================

::: {.section .multi-line-signature}
[Set](../../dart-core/set-class)\<R\> cast\<R\>()

::: {.features}
override
:::
:::

Provides a view of this set as a set of `R` instances.

If this set contains only instances of `R`, all read operations will
work correctly. If any operation tries to access an element that is not
an instance of `R`, the access will throw instead.

Elements added to the set (e.g., by using [add](add) or
[addAll](addall)) must be instances of `R` to be valid arguments to the
adding function, and they must be instances of `E` as well to be
accepted by this set as well.

Methods which accept one or more `Object?` as argument, like
[contains](contains), [remove](remove) and [removeAll](removeall), will
pass the argument directly to the this set\'s method without any checks.
That means that you can do `setOfStrings.cast<int>().remove("a")`
successfully, even if it looks like it shouldn\'t have any effect.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Set<R> cast<R>() => Set.castFrom<E, R>(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SetMixin/cast.html>
:::

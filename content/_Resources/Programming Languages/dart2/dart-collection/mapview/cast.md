[dart:collection](../../dart-collection/dart-collection-library){._links-link}

cast\<RK, RV\> method
=====================

::: {.section .multi-line-signature}
[Map](../../dart-core/map-class)\<RK, RV\> cast\<RK, RV\>()

::: {.features}
override
:::
:::

Provides a view of this map as having `RK` keys and `RV` instances, if
necessary.

If this map is already a `Map<RK, RV>`, it is returned unchanged.

If this set contains only keys of type `RK` and values of type `RV`, all
read operations will work correctly. If any operation exposes a non-`RK`
key or non-`RV` value, the operation will throw instead.

Entries added to the map must be valid for both a `Map<K, V>` and a
`Map<RK, RV>`.

Methods which accept `Object?` as argument, like
[containsKey](containskey), [remove](remove) and [operator
\[\]](operator_get), will pass the argument directly to the this map\'s
method without any checks. That means that you can do
`mapWithStringKeys.cast<int,int>().remove("a")` successfully, even if it
looks like it shouldn\'t have any effect.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Map<RK, RV> cast<RK, RV>() => _map.cast<RK, RV>();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/MapView/cast.html>
:::

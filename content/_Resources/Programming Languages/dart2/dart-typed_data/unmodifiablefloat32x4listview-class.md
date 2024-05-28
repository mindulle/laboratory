[dart:typed\_data](../dart-typed_data/dart-typed_data-library){._links-link}

UnmodifiableFloat32x4ListView class
===================================

View of a [Float32x4List](float32x4list-class) that disallows
modification.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [ListBase](../dart-collection/listbase-class)\<[Float32x4](float32x4-class)\>
    -   UnmodifiableFloat32x4ListView

Implemented types

:   -   [Float32x4List](float32x4list-class)

Available Extensions

:   -   [EnumByName](../dart-core/enumbyname)

Constructors
------------

[UnmodifiableFloat32x4ListView](unmodifiablefloat32x4listview/unmodifiablefloat32x4listview)([Float32x4List](float32x4list-class)
list)

Properties {#instance-properties}
----------

[buffer](unmodifiablefloat32x4listview/buffer) →
[ByteBuffer](bytebuffer-class)

::: {.features}
read-only, inherited
:::

[elementSizeInBytes](unmodifiablefloat32x4listview/elementsizeinbytes) →
[int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

[first](../dart-collection/listmixin/first) ↔
[Float32x4](float32x4-class)

::: {.features}
read / write, inherited
:::

Returns the first element.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isEmpty](../dart-collection/listmixin/isempty) →
[bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Whether this collection has no elements.

[isNotEmpty](../dart-collection/listmixin/isnotempty) →
[bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Whether this collection has at least one element.

[iterator](../dart-collection/listmixin/iterator) →
[Iterator](../dart-core/iterator-class)\<[Float32x4](float32x4-class)\>

::: {.features}
read-only, inherited
:::

Returns a new `Iterator` that allows iterating the elements of this
`Iterable`.

[last](../dart-collection/listmixin/last) ↔ [Float32x4](float32x4-class)

::: {.features}
read / write, inherited
:::

Returns the last element.

[length](unmodifiablefloat32x4listview/length) ↔
[int](../dart-core/int-class)

::: {.features}
read / write, inherited
:::

This operation is not supported by an unmodifiable list.

[lengthInBytes](unmodifiablefloat32x4listview/lengthinbytes) →
[int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

[offsetInBytes](unmodifiablefloat32x4listview/offsetinbytes) →
[int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

[reversed](../dart-collection/listmixin/reversed) →
[Iterable](../dart-core/iterable-class)\<[Float32x4](float32x4-class)\>

::: {.features}
read-only, inherited
:::

An [Iterable](../dart-core/iterable-class) of the objects in this list
in reverse order.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[single](../dart-collection/listmixin/single) →
[Float32x4](float32x4-class)

::: {.features}
read-only, inherited
:::

Checks that this iterable has only one element, and returns that
element.

Methods {#instance-methods}
-------

[add](unmodifiablefloat32x4listview/add)([Float32x4](float32x4-class)
value) → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable list.

[addAll](unmodifiablefloat32x4listview/addall)([Iterable](../dart-core/iterable-class)\<[Float32x4](float32x4-class)\>
iterable) → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable list.

[any](../dart-collection/listmixin/any)([bool](../dart-core/bool-class)
test([Float32x4](float32x4-class) element)) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Checks whether any element of this iterable satisfies `test`.

[asMap](../dart-collection/listmixin/asmap)() →
[Map](../dart-core/map-class)\<[int](../dart-core/int-class),
[Float32x4](float32x4-class)\>

::: {.features}
inherited
:::

An unmodifiable [Map](../dart-core/map-class) view of this list.

[cast](../dart-collection/listmixin/cast)\<R\>() →
[List](../dart-core/list-class)\<R\>

::: {.features}
inherited
:::

Returns a view of this list as a list of `R` instances.

[clear](unmodifiablefloat32x4listview/clear)() → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable list.

[contains](../dart-collection/listmixin/contains)([Object](../dart-core/object-class)?
element) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Whether the collection contains an element equal to `element`.

[elementAt](../dart-collection/listmixin/elementat)([int](../dart-core/int-class)
index) → [Float32x4](float32x4-class)

::: {.features}
inherited
:::

Returns the `index`th element.

[every](../dart-collection/listmixin/every)([bool](../dart-core/bool-class)
test([Float32x4](float32x4-class) element)) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Checks whether every element of this iterable satisfies `test`.

[expand](../dart-collection/listmixin/expand)\<T\>([Iterable](../dart-core/iterable-class)\<T\>
f([Float32x4](float32x4-class) element)) →
[Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
inherited
:::

Expands each element of this [Iterable](../dart-core/iterable-class)
into zero or more elements.

[fillRange](unmodifiablefloat32x4listview/fillrange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end,
\[[Float32x4](float32x4-class)? fillValue\]) → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable list.

[firstWhere](../dart-collection/listmixin/firstwhere)([bool](../dart-core/bool-class)
test([Float32x4](float32x4-class) element),
{[Float32x4](float32x4-class) orElse()?}) → [Float32x4](float32x4-class)

::: {.features}
inherited
:::

Returns the first element that satisfies the given predicate `test`.

[fold](../dart-collection/listmixin/fold)\<T\>(T initialValue, T
combine(T previousValue, [Float32x4](float32x4-class) element)) → T

::: {.features}
inherited
:::

Reduces a collection to a single value by iteratively combining each
element of the collection with an existing value

[followedBy](../dart-collection/listmixin/followedby)([Iterable](../dart-core/iterable-class)\<[Float32x4](float32x4-class)\>
other) →
[Iterable](../dart-core/iterable-class)\<[Float32x4](float32x4-class)\>

::: {.features}
inherited
:::

Returns the lazy concatenation of this iterable and `other`.

[forEach](../dart-collection/listmixin/foreach)(void
action([Float32x4](float32x4-class) element)) → void

::: {.features}
inherited
:::

Invokes `action` on each element of this iterable in iteration order.

[getRange](../dart-collection/listmixin/getrange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end) →
[Iterable](../dart-core/iterable-class)\<[Float32x4](float32x4-class)\>

::: {.features}
inherited
:::

Creates an [Iterable](../dart-core/iterable-class) that iterates over a
range of elements.

[indexOf](../dart-collection/listmixin/indexof)([Object](../dart-core/object-class)?
element, \[[int](../dart-core/int-class) start = 0\]) →
[int](../dart-core/int-class)

::: {.features}
inherited
:::

The first index of `element` in this list.

[indexWhere](../dart-collection/listmixin/indexwhere)([bool](../dart-core/bool-class)
test([Float32x4](float32x4-class) element),
\[[int](../dart-core/int-class) start = 0\]) →
[int](../dart-core/int-class)

::: {.features}
inherited
:::

The first index in the list that satisfies the provided `test`.

[insert](unmodifiablefloat32x4listview/insert)([int](../dart-core/int-class)
index, [Float32x4](float32x4-class) element) → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable list.

[insertAll](unmodifiablefloat32x4listview/insertall)([int](../dart-core/int-class)
at,
[Iterable](../dart-core/iterable-class)\<[Float32x4](float32x4-class)\>
iterable) → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable list.

[join](../dart-collection/listmixin/join)(\[[String](../dart-core/string-class)
separator = \"\"\]) → [String](../dart-core/string-class)

::: {.features}
inherited
:::

Converts each element to a [String](../dart-core/string-class) and
concatenates the strings.

[lastIndexOf](../dart-collection/listmixin/lastindexof)([Object](../dart-core/object-class)?
element, \[[int](../dart-core/int-class)? start\]) →
[int](../dart-core/int-class)

::: {.features}
inherited
:::

The last index of `element` in this list.

[lastIndexWhere](../dart-collection/listmixin/lastindexwhere)([bool](../dart-core/bool-class)
test([Float32x4](float32x4-class) element),
\[[int](../dart-core/int-class)? start\]) →
[int](../dart-core/int-class)

::: {.features}
inherited
:::

The last index in the list that satisfies the provided `test`.

[lastWhere](../dart-collection/listmixin/lastwhere)([bool](../dart-core/bool-class)
test([Float32x4](float32x4-class) element),
{[Float32x4](float32x4-class) orElse()?}) → [Float32x4](float32x4-class)

::: {.features}
inherited
:::

Returns the last element that satisfies the given predicate `test`.

[map](../dart-collection/listmixin/map)\<T\>(T
f([Float32x4](float32x4-class) element)) →
[Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
inherited
:::

The current elements of this iterable modified by `toElement`.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[reduce](../dart-collection/listmixin/reduce)([Float32x4](float32x4-class)
combine([Float32x4](float32x4-class) previousValue,
[Float32x4](float32x4-class) element)) → [Float32x4](float32x4-class)

::: {.features}
inherited
:::

Reduces a collection to a single value by iteratively combining elements
of the collection using the provided function.

[remove](unmodifiablefloat32x4listview/remove)([Object](../dart-core/object-class)?
element) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable list.

[removeAt](unmodifiablefloat32x4listview/removeat)([int](../dart-core/int-class)
index) → [Float32x4](float32x4-class)

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable list.

[removeLast](unmodifiablefloat32x4listview/removelast)() →
[Float32x4](float32x4-class)

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable list.

[removeRange](unmodifiablefloat32x4listview/removerange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end) → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable list.

[removeWhere](unmodifiablefloat32x4listview/removewhere)([bool](../dart-core/bool-class)
test([Float32x4](float32x4-class) element)) → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable list.

[replaceRange](unmodifiablefloat32x4listview/replacerange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end,
[Iterable](../dart-core/iterable-class)\<[Float32x4](float32x4-class)\>
iterable) → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable list.

[retainWhere](unmodifiablefloat32x4listview/retainwhere)([bool](../dart-core/bool-class)
test([Float32x4](float32x4-class) element)) → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable list.

[setAll](unmodifiablefloat32x4listview/setall)([int](../dart-core/int-class)
at,
[Iterable](../dart-core/iterable-class)\<[Float32x4](float32x4-class)\>
iterable) → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable list.

[setRange](unmodifiablefloat32x4listview/setrange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end,
[Iterable](../dart-core/iterable-class)\<[Float32x4](float32x4-class)\>
iterable, \[[int](../dart-core/int-class) skipCount = 0\]) → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable list.

[shuffle](unmodifiablefloat32x4listview/shuffle)(\[[Random](../dart-math/random-class)?
random\]) → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable list.

[singleWhere](../dart-collection/listmixin/singlewhere)([bool](../dart-core/bool-class)
test([Float32x4](float32x4-class) element),
{[Float32x4](float32x4-class) orElse()?}) → [Float32x4](float32x4-class)

::: {.features}
inherited
:::

Returns the single element that satisfies `test`.

[skip](../dart-collection/listmixin/skip)([int](../dart-core/int-class)
count) →
[Iterable](../dart-core/iterable-class)\<[Float32x4](float32x4-class)\>

::: {.features}
inherited
:::

Returns an [Iterable](../dart-core/iterable-class) that provides all but
the first `count` elements.

[skipWhile](../dart-collection/listmixin/skipwhile)([bool](../dart-core/bool-class)
test([Float32x4](float32x4-class) element)) →
[Iterable](../dart-core/iterable-class)\<[Float32x4](float32x4-class)\>

::: {.features}
inherited
:::

Returns an `Iterable` that skips leading elements while `test` is
satisfied.

[sort](unmodifiablefloat32x4listview/sort)(\[[Comparator](../dart-core/comparator)\<[Float32x4](float32x4-class)\>?
compare\]) → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable list.

[sublist](unmodifiablefloat32x4listview/sublist)([int](../dart-core/int-class)
start, \[[int](../dart-core/int-class)? end\]) →
[Float32x4List](float32x4list-class)

::: {.features}
inherited
:::

[take](../dart-collection/listmixin/take)([int](../dart-core/int-class)
count) →
[Iterable](../dart-core/iterable-class)\<[Float32x4](float32x4-class)\>

::: {.features}
inherited
:::

Returns a lazy iterable of the `count` first elements of this iterable.

[takeWhile](../dart-collection/listmixin/takewhile)([bool](../dart-core/bool-class)
test([Float32x4](float32x4-class) element)) →
[Iterable](../dart-core/iterable-class)\<[Float32x4](float32x4-class)\>

::: {.features}
inherited
:::

Returns a lazy iterable of the leading elements satisfying `test`.

[toList](../dart-collection/listmixin/tolist)({[bool](../dart-core/bool-class)
growable = true}) →
[List](../dart-core/list-class)\<[Float32x4](float32x4-class)\>

::: {.features}
inherited
:::

Creates a [List](../dart-core/list-class) containing the elements of
this [Iterable](../dart-core/iterable-class).

[toSet](../dart-collection/listmixin/toset)() →
[Set](../dart-core/set-class)\<[Float32x4](float32x4-class)\>

::: {.features}
inherited
:::

Creates a [Set](../dart-core/set-class) containing the same elements as
this iterable.

[toString](../dart-collection/listmixin/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[where](../dart-collection/listmixin/where)([bool](../dart-core/bool-class)
test([Float32x4](float32x4-class) element)) →
[Iterable](../dart-core/iterable-class)\<[Float32x4](float32x4-class)\>

::: {.features}
inherited
:::

Returns a new lazy [Iterable](../dart-core/iterable-class) with all
elements that satisfy the predicate `test`.

[whereType](../dart-collection/listmixin/wheretype)\<T\>() →
[Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
inherited
:::

Returns a new lazy [Iterable](../dart-core/iterable-class) with all
elements that have type `T`.

Operators
---------

[operator
+](../dart-collection/listmixin/operator_plus)([List](../dart-core/list-class)\<[Float32x4](float32x4-class)\>
other) → [List](../dart-core/list-class)\<[Float32x4](float32x4-class)\>

::: {.features}
inherited
:::

Returns the concatenation of this list and `other`.

[operator
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

[operator
\[\]](unmodifiablefloat32x4listview/operator_get)([int](../dart-core/int-class)
index) → [Float32x4](float32x4-class)

::: {.features}
inherited
:::

[operator
\[\]=](unmodifiablefloat32x4listview/operator_put)([int](../dart-core/int-class)
index, [Float32x4](float32x4-class) value) → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable list.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/UnmodifiableFloat32x4ListView-class.html>
:::

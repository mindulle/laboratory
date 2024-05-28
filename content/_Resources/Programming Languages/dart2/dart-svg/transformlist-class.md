[dart:svg](../dart-svg/dart-svg-library){._links-link}

TransformList class
===================

Implemented types

:   -   [List](../dart-core/list-class)\<[Transform](transform-class)\>

Mixed in types

:   -   [ListMixin](../dart-collection/listmixin-class)\<[Transform](transform-class)\>
    -   [ImmutableListMixin](../dart-html/immutablelistmixin-class)\<[Transform](transform-class)\>

Available Extensions

:   -   [EnumByName](../dart-core/enumbyname)

Annotations

:   -   \@Unstable()
    -   \@Native(\"SVGTransformList\")

Properties {#instance-properties}
----------

[first](transformlist/first) ↔ [Transform](transform-class)

::: {.features}
read / write, inherited-setter, override-getter
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

[iterator](../dart-html/immutablelistmixin/iterator) →
[Iterator](../dart-core/iterator-class)\<[Transform](transform-class)\>

::: {.features}
read-only, inherited
:::

Returns a new `Iterator` that allows iterating the elements of this
`Iterable`.

[last](transformlist/last) ↔ [Transform](transform-class)

::: {.features}
read / write, inherited-setter, override-getter
:::

Returns the last element.

[length](transformlist/length) ↔ [int](../dart-core/int-class)

::: {.features}
read / write, override
:::

The number of objects in this list.

[numberOfItems](transformlist/numberofitems) →
[int](../dart-core/int-class)?

::: {.features}
read-only
:::

[reversed](../dart-collection/listmixin/reversed) →
[Iterable](../dart-core/iterable-class)\<[Transform](transform-class)\>

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

[single](transformlist/single) → [Transform](transform-class)

::: {.features}
read-only, override
:::

Checks that this iterable has only one element, and returns that
element.

Methods {#instance-methods}
-------

[add](../dart-html/immutablelistmixin/add)([Transform](transform-class)
value) → void

::: {.features}
inherited
:::

Adds `value` to the end of this list, extending the length by one.

[addAll](../dart-html/immutablelistmixin/addall)([Iterable](../dart-core/iterable-class)\<[Transform](transform-class)\>
iterable) → void

::: {.features}
inherited
:::

Appends all objects of `iterable` to the end of this list.

[any](../dart-collection/listmixin/any)([bool](../dart-core/bool-class)
test([Transform](transform-class) element)) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Checks whether any element of this iterable satisfies `test`.

[appendItem](transformlist/appenditem)([Transform](transform-class)
newItem) → [Transform](transform-class)

[asMap](../dart-collection/listmixin/asmap)() →
[Map](../dart-core/map-class)\<[int](../dart-core/int-class),
[Transform](transform-class)\>

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

[clear](transformlist/clear)() → void

::: {.features}
override
:::

Removes all objects from this list; the length of the list becomes zero.

[consolidate](transformlist/consolidate)() →
[Transform](transform-class)?

[contains](../dart-collection/listmixin/contains)([Object](../dart-core/object-class)?
element) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Whether the collection contains an element equal to `element`.

[createSvgTransformFromMatrix](transformlist/createsvgtransformfrommatrix)([Matrix](matrix-class)
matrix) → [Transform](transform-class)

::: {.features}
\@JSName(\'createSVGTransformFromMatrix\')
:::

[elementAt](transformlist/elementat)([int](../dart-core/int-class)
index) → [Transform](transform-class)

::: {.features}
override
:::

Returns the `index`th element.

[every](../dart-collection/listmixin/every)([bool](../dart-core/bool-class)
test([Transform](transform-class) element)) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Checks whether every element of this iterable satisfies `test`.

[expand](../dart-collection/listmixin/expand)\<T\>([Iterable](../dart-core/iterable-class)\<T\>
f([Transform](transform-class) element)) →
[Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
inherited
:::

Expands each element of this [Iterable](../dart-core/iterable-class)
into zero or more elements.

[fillRange](../dart-html/immutablelistmixin/fillrange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end,
\[[Transform](transform-class)? fillValue\]) → void

::: {.features}
inherited
:::

Overwrites a range of elements with `fillValue`.

[firstWhere](../dart-collection/listmixin/firstwhere)([bool](../dart-core/bool-class)
test([Transform](transform-class) element),
{[Transform](transform-class) orElse()?}) → [Transform](transform-class)

::: {.features}
inherited
:::

Returns the first element that satisfies the given predicate `test`.

[fold](../dart-collection/listmixin/fold)\<T\>(T initialValue, T
combine(T previousValue, [Transform](transform-class) element)) → T

::: {.features}
inherited
:::

Reduces a collection to a single value by iteratively combining each
element of the collection with an existing value

[followedBy](../dart-collection/listmixin/followedby)([Iterable](../dart-core/iterable-class)\<[Transform](transform-class)\>
other) →
[Iterable](../dart-core/iterable-class)\<[Transform](transform-class)\>

::: {.features}
inherited
:::

Returns the lazy concatenation of this iterable and `other`.

[forEach](../dart-collection/listmixin/foreach)(void
action([Transform](transform-class) element)) → void

::: {.features}
inherited
:::

Invokes `action` on each element of this iterable in iteration order.

[getItem](transformlist/getitem)([int](../dart-core/int-class) index) →
[Transform](transform-class)

[getRange](../dart-collection/listmixin/getrange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end) →
[Iterable](../dart-core/iterable-class)\<[Transform](transform-class)\>

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
test([Transform](transform-class) element),
\[[int](../dart-core/int-class) start = 0\]) →
[int](../dart-core/int-class)

::: {.features}
inherited
:::

The first index in the list that satisfies the provided `test`.

[initialize](transformlist/initialize)([Transform](transform-class)
newItem) → [Transform](transform-class)

[insert](../dart-html/immutablelistmixin/insert)([int](../dart-core/int-class)
index, [Transform](transform-class) element) → void

::: {.features}
inherited
:::

Inserts `element` at position `index` in this list.

[insertAll](../dart-html/immutablelistmixin/insertall)([int](../dart-core/int-class)
index,
[Iterable](../dart-core/iterable-class)\<[Transform](transform-class)\>
iterable) → void

::: {.features}
inherited
:::

Inserts all objects of `iterable` at position `index` in this list.

[insertItemBefore](transformlist/insertitembefore)([Transform](transform-class)
newItem, [int](../dart-core/int-class) index) →
[Transform](transform-class)

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
test([Transform](transform-class) element),
\[[int](../dart-core/int-class)? start\]) →
[int](../dart-core/int-class)

::: {.features}
inherited
:::

The last index in the list that satisfies the provided `test`.

[lastWhere](../dart-collection/listmixin/lastwhere)([bool](../dart-core/bool-class)
test([Transform](transform-class) element),
{[Transform](transform-class) orElse()?}) → [Transform](transform-class)

::: {.features}
inherited
:::

Returns the last element that satisfies the given predicate `test`.

[map](../dart-collection/listmixin/map)\<T\>(T
f([Transform](transform-class) element)) →
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

[reduce](../dart-collection/listmixin/reduce)([Transform](transform-class)
combine([Transform](transform-class) previousValue,
[Transform](transform-class) element)) → [Transform](transform-class)

::: {.features}
inherited
:::

Reduces a collection to a single value by iteratively combining elements
of the collection using the provided function.

[remove](../dart-html/immutablelistmixin/remove)([Object](../dart-core/object-class)?
object) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Removes the first occurrence of `value` from this list.

[removeAt](../dart-html/immutablelistmixin/removeat)([int](../dart-core/int-class)
pos) → [Transform](transform-class)

::: {.features}
inherited
:::

Removes the object at position `index` from this list.

[removeItem](transformlist/removeitem)([int](../dart-core/int-class)
index) → [Transform](transform-class)

[removeLast](../dart-html/immutablelistmixin/removelast)() →
[Transform](transform-class)

::: {.features}
inherited
:::

Removes and returns the last object in this list.

[removeRange](../dart-html/immutablelistmixin/removerange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end) → void

::: {.features}
inherited
:::

Removes a range of elements from the list.

[removeWhere](../dart-html/immutablelistmixin/removewhere)([bool](../dart-core/bool-class)
test([Transform](transform-class) element)) → void

::: {.features}
inherited
:::

Removes all objects from this list that satisfy `test`.

[replaceItem](transformlist/replaceitem)([Transform](transform-class)
newItem, [int](../dart-core/int-class) index) →
[Transform](transform-class)

[replaceRange](../dart-html/immutablelistmixin/replacerange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end,
[Iterable](../dart-core/iterable-class)\<[Transform](transform-class)\>
iterable) → void

::: {.features}
inherited
:::

Replaces a range of elements with the elements of `replacements`.

[retainWhere](../dart-html/immutablelistmixin/retainwhere)([bool](../dart-core/bool-class)
test([Transform](transform-class) element)) → void

::: {.features}
inherited
:::

Removes all objects from this list that fail to satisfy `test`.

[setAll](../dart-html/immutablelistmixin/setall)([int](../dart-core/int-class)
index,
[Iterable](../dart-core/iterable-class)\<[Transform](transform-class)\>
iterable) → void

::: {.features}
inherited
:::

Overwrites elements with the objects of `iterable`.

[setRange](../dart-html/immutablelistmixin/setrange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end,
[Iterable](../dart-core/iterable-class)\<[Transform](transform-class)\>
iterable, \[[int](../dart-core/int-class) skipCount = 0\]) → void

::: {.features}
inherited
:::

Writes some elements of `iterable` into a range of this list.

[shuffle](../dart-html/immutablelistmixin/shuffle)(\[[Random](../dart-math/random-class)?
random\]) → void

::: {.features}
inherited
:::

Shuffles the elements of this list randomly.

[singleWhere](../dart-collection/listmixin/singlewhere)([bool](../dart-core/bool-class)
test([Transform](transform-class) element),
{[Transform](transform-class) orElse()?}) → [Transform](transform-class)

::: {.features}
inherited
:::

Returns the single element that satisfies `test`.

[skip](../dart-collection/listmixin/skip)([int](../dart-core/int-class)
count) →
[Iterable](../dart-core/iterable-class)\<[Transform](transform-class)\>

::: {.features}
inherited
:::

Returns an [Iterable](../dart-core/iterable-class) that provides all but
the first `count` elements.

[skipWhile](../dart-collection/listmixin/skipwhile)([bool](../dart-core/bool-class)
test([Transform](transform-class) element)) →
[Iterable](../dart-core/iterable-class)\<[Transform](transform-class)\>

::: {.features}
inherited
:::

Returns an `Iterable` that skips leading elements while `test` is
satisfied.

[sort](../dart-html/immutablelistmixin/sort)(\[[int](../dart-core/int-class)
compare([Transform](transform-class) a, [Transform](transform-class)
b)?\]) → void

::: {.features}
inherited
:::

Sorts this list according to the order specified by the `compare`
function.

[sublist](../dart-collection/listmixin/sublist)([int](../dart-core/int-class)
start, \[[int](../dart-core/int-class)? end\]) →
[List](../dart-core/list-class)\<[Transform](transform-class)\>

::: {.features}
inherited
:::

Returns a new list containing the elements between `start` and `end`.

[take](../dart-collection/listmixin/take)([int](../dart-core/int-class)
count) →
[Iterable](../dart-core/iterable-class)\<[Transform](transform-class)\>

::: {.features}
inherited
:::

Returns a lazy iterable of the `count` first elements of this iterable.

[takeWhile](../dart-collection/listmixin/takewhile)([bool](../dart-core/bool-class)
test([Transform](transform-class) element)) →
[Iterable](../dart-core/iterable-class)\<[Transform](transform-class)\>

::: {.features}
inherited
:::

Returns a lazy iterable of the leading elements satisfying `test`.

[toList](../dart-collection/listmixin/tolist)({[bool](../dart-core/bool-class)
growable = true}) →
[List](../dart-core/list-class)\<[Transform](transform-class)\>

::: {.features}
inherited
:::

Creates a [List](../dart-core/list-class) containing the elements of
this [Iterable](../dart-core/iterable-class).

[toSet](../dart-collection/listmixin/toset)() →
[Set](../dart-core/set-class)\<[Transform](transform-class)\>

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
test([Transform](transform-class) element)) →
[Iterable](../dart-core/iterable-class)\<[Transform](transform-class)\>

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
+](../dart-collection/listmixin/operator_plus)([List](../dart-core/list-class)\<[Transform](transform-class)\>
other) → [List](../dart-core/list-class)\<[Transform](transform-class)\>

::: {.features}
inherited
:::

Returns the concatenation of this list and `other`.

[operator
==](../dart-core/list/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

[operator
\[\]](transformlist/operator_get)([int](../dart-core/int-class) index) →
[Transform](transform-class)

::: {.features}
override
:::

The object at the given `index` in the list.

[operator
\[\]=](transformlist/operator_put)([int](../dart-core/int-class) index,
[Transform](transform-class) value) → void

::: {.features}
override
:::

Sets the value at the given `index` in the list to `value`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/TransformList-class.html>
:::

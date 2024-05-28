[dart:typed\_data](../dart-typed_data/dart-typed_data-library){._links-link}

Float32x4List class
===================

A fixed-length list of Float32x4 numbers that is viewable as a
[TypedData](typeddata-class).

For long lists, this implementation will be considerably more space- and
time-efficient than the default [List](../dart-core/list-class)
implementation.

Implemented types

:   -   [List](../dart-core/list-class)\<[Float32x4](float32x4-class)\>
    -   [TypedData](typeddata-class)

Implementers

:   -   [UnmodifiableFloat32x4ListView](unmodifiablefloat32x4listview-class)

Available Extensions

:   -   [EnumByName](../dart-core/enumbyname)

Constructors
------------

[Float32x4List](float32x4list/float32x4list)([int](../dart-core/int-class)
length)

::: {.constructor-modifier .features}
factory
:::

Creates a [Float32x4List](float32x4list-class) of the specified length
(in elements), all of whose elements are initially zero.

[Float32x4List.fromList](float32x4list/float32x4list.fromlist)([List](../dart-core/list-class)\<[Float32x4](float32x4-class)\>
elements)

::: {.constructor-modifier .features}
factory
:::

Creates a [Float32x4List](float32x4list-class) with the same length as
the `elements` list and copies over the elements.

[Float32x4List.sublistView](float32x4list/float32x4list.sublistview)([TypedData](typeddata-class)
data, \[[int](../dart-core/int-class) start = 0,
[int](../dart-core/int-class)? end\])

::: {.constructor-modifier .features}
factory
:::

Creates a [Float32x4List](float32x4list-class) view on a range of
elements of `data`.

[Float32x4List.view](float32x4list/float32x4list.view)([ByteBuffer](bytebuffer-class)
buffer, \[[int](../dart-core/int-class) offsetInBytes = 0,
[int](../dart-core/int-class)? length\])

::: {.constructor-modifier .features}
factory
:::

Creates a [Float32x4List](float32x4list-class) *view* of the specified
region in `buffer`.

Properties {#instance-properties}
----------

[buffer](typeddata/buffer) → [ByteBuffer](bytebuffer-class)

::: {.features}
read-only, inherited
:::

Returns the byte buffer associated with this object.

[elementSizeInBytes](typeddata/elementsizeinbytes) →
[int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

Returns the number of bytes in the representation of each element in
this list.

[first](../dart-core/iterable/first) ↔ [Float32x4](float32x4-class)

::: {.features}
read / write, inherited
:::

Returns the first element.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isEmpty](../dart-core/iterable/isempty) →
[bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Whether this collection has no elements.

[isNotEmpty](../dart-core/iterable/isnotempty) →
[bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Whether this collection has at least one element.

[iterator](../dart-core/iterable/iterator) →
[Iterator](../dart-core/iterator-class)\<[Float32x4](float32x4-class)\>

::: {.features}
read-only, inherited
:::

Returns a new `Iterator` that allows iterating the elements of this
`Iterable`.

[last](../dart-core/iterable/last) ↔ [Float32x4](float32x4-class)

::: {.features}
read / write, inherited
:::

Returns the last element.

[length](../dart-core/list/length) ↔ [int](../dart-core/int-class)

::: {.features}
read / write, inherited
:::

The number of objects in this list.

[lengthInBytes](typeddata/lengthinbytes) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

Returns the length of this view, in bytes.

[offsetInBytes](typeddata/offsetinbytes) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

Returns the offset in bytes into the underlying byte buffer of this
view.

[reversed](../dart-core/list/reversed) →
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

[single](../dart-core/iterable/single) → [Float32x4](float32x4-class)

::: {.features}
read-only, inherited
:::

Checks that this iterable has only one element, and returns that
element.

Methods {#instance-methods}
-------

[add](../dart-core/list/add)([Float32x4](float32x4-class) value) → void

::: {.features}
inherited
:::

Adds `value` to the end of this list, extending the length by one.

[addAll](../dart-core/list/addall)([Iterable](../dart-core/iterable-class)\<[Float32x4](float32x4-class)\>
iterable) → void

::: {.features}
inherited
:::

Appends all objects of `iterable` to the end of this list.

[any](../dart-core/iterable/any)([bool](../dart-core/bool-class)
test([Float32x4](float32x4-class) element)) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Checks whether any element of this iterable satisfies `test`.

[asMap](../dart-core/list/asmap)() →
[Map](../dart-core/map-class)\<[int](../dart-core/int-class),
[Float32x4](float32x4-class)\>

::: {.features}
inherited
:::

An unmodifiable [Map](../dart-core/map-class) view of this list.

[cast](../dart-core/list/cast)\<R\>() →
[List](../dart-core/list-class)\<R\>

::: {.features}
inherited
:::

Returns a view of this list as a list of `R` instances.

[clear](../dart-core/list/clear)() → void

::: {.features}
inherited
:::

Removes all objects from this list; the length of the list becomes zero.

[contains](../dart-core/iterable/contains)([Object](../dart-core/object-class)?
element) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Whether the collection contains an element equal to `element`.

[elementAt](../dart-core/iterable/elementat)([int](../dart-core/int-class)
index) → [Float32x4](float32x4-class)

::: {.features}
inherited
:::

Returns the `index`th element.

[every](../dart-core/iterable/every)([bool](../dart-core/bool-class)
test([Float32x4](float32x4-class) element)) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Checks whether every element of this iterable satisfies `test`.

[expand](../dart-core/iterable/expand)\<T\>([Iterable](../dart-core/iterable-class)\<T\>
toElements([Float32x4](float32x4-class) element)) →
[Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
inherited
:::

Expands each element of this [Iterable](../dart-core/iterable-class)
into zero or more elements.

[fillRange](../dart-core/list/fillrange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end,
\[[Float32x4](float32x4-class)? fillValue\]) → void

::: {.features}
inherited
:::

Overwrites a range of elements with `fillValue`.

[firstWhere](../dart-core/iterable/firstwhere)([bool](../dart-core/bool-class)
test([Float32x4](float32x4-class) element),
{[Float32x4](float32x4-class) orElse()?}) → [Float32x4](float32x4-class)

::: {.features}
inherited
:::

Returns the first element that satisfies the given predicate `test`.

[fold](../dart-core/iterable/fold)\<T\>(T initialValue, T combine(T
previousValue, [Float32x4](float32x4-class) element)) → T

::: {.features}
inherited
:::

Reduces a collection to a single value by iteratively combining each
element of the collection with an existing value

[followedBy](../dart-core/iterable/followedby)([Iterable](../dart-core/iterable-class)\<[Float32x4](float32x4-class)\>
other) →
[Iterable](../dart-core/iterable-class)\<[Float32x4](float32x4-class)\>

::: {.features}
inherited
:::

Returns the lazy concatenation of this iterable and `other`.

[forEach](../dart-core/iterable/foreach)(void
action([Float32x4](float32x4-class) element)) → void

::: {.features}
inherited
:::

Invokes `action` on each element of this iterable in iteration order.

[getRange](../dart-core/list/getrange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end) →
[Iterable](../dart-core/iterable-class)\<[Float32x4](float32x4-class)\>

::: {.features}
inherited
:::

Creates an [Iterable](../dart-core/iterable-class) that iterates over a
range of elements.

[indexOf](../dart-core/list/indexof)([Float32x4](float32x4-class)
element, \[[int](../dart-core/int-class) start = 0\]) →
[int](../dart-core/int-class)

::: {.features}
inherited
:::

The first index of `element` in this list.

[indexWhere](../dart-core/list/indexwhere)([bool](../dart-core/bool-class)
test([Float32x4](float32x4-class) element),
\[[int](../dart-core/int-class) start = 0\]) →
[int](../dart-core/int-class)

::: {.features}
inherited
:::

The first index in the list that satisfies the provided `test`.

[insert](../dart-core/list/insert)([int](../dart-core/int-class) index,
[Float32x4](float32x4-class) element) → void

::: {.features}
inherited
:::

Inserts `element` at position `index` in this list.

[insertAll](../dart-core/list/insertall)([int](../dart-core/int-class)
index,
[Iterable](../dart-core/iterable-class)\<[Float32x4](float32x4-class)\>
iterable) → void

::: {.features}
inherited
:::

Inserts all objects of `iterable` at position `index` in this list.

[join](../dart-core/iterable/join)(\[[String](../dart-core/string-class)
separator = \"\"\]) → [String](../dart-core/string-class)

::: {.features}
inherited
:::

Converts each element to a [String](../dart-core/string-class) and
concatenates the strings.

[lastIndexOf](../dart-core/list/lastindexof)([Float32x4](float32x4-class)
element, \[[int](../dart-core/int-class)? start\]) →
[int](../dart-core/int-class)

::: {.features}
inherited
:::

The last index of `element` in this list.

[lastIndexWhere](../dart-core/list/lastindexwhere)([bool](../dart-core/bool-class)
test([Float32x4](float32x4-class) element),
\[[int](../dart-core/int-class)? start\]) →
[int](../dart-core/int-class)

::: {.features}
inherited
:::

The last index in the list that satisfies the provided `test`.

[lastWhere](../dart-core/iterable/lastwhere)([bool](../dart-core/bool-class)
test([Float32x4](float32x4-class) element),
{[Float32x4](float32x4-class) orElse()?}) → [Float32x4](float32x4-class)

::: {.features}
inherited
:::

Returns the last element that satisfies the given predicate `test`.

[map](../dart-core/iterable/map)\<T\>(T
toElement([Float32x4](float32x4-class) e)) →
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

[reduce](../dart-core/iterable/reduce)([Float32x4](float32x4-class)
combine([Float32x4](float32x4-class) value, [Float32x4](float32x4-class)
element)) → [Float32x4](float32x4-class)

::: {.features}
inherited
:::

Reduces a collection to a single value by iteratively combining elements
of the collection using the provided function.

[remove](../dart-core/list/remove)([Object](../dart-core/object-class)?
value) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Removes the first occurrence of `value` from this list.

[removeAt](../dart-core/list/removeat)([int](../dart-core/int-class)
index) → [Float32x4](float32x4-class)

::: {.features}
inherited
:::

Removes the object at position `index` from this list.

[removeLast](../dart-core/list/removelast)() →
[Float32x4](float32x4-class)

::: {.features}
inherited
:::

Removes and returns the last object in this list.

[removeRange](../dart-core/list/removerange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end) → void

::: {.features}
inherited
:::

Removes a range of elements from the list.

[removeWhere](../dart-core/list/removewhere)([bool](../dart-core/bool-class)
test([Float32x4](float32x4-class) element)) → void

::: {.features}
inherited
:::

Removes all objects from this list that satisfy `test`.

[replaceRange](../dart-core/list/replacerange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end,
[Iterable](../dart-core/iterable-class)\<[Float32x4](float32x4-class)\>
replacements) → void

::: {.features}
inherited
:::

Replaces a range of elements with the elements of `replacements`.

[retainWhere](../dart-core/list/retainwhere)([bool](../dart-core/bool-class)
test([Float32x4](float32x4-class) element)) → void

::: {.features}
inherited
:::

Removes all objects from this list that fail to satisfy `test`.

[setAll](../dart-core/list/setall)([int](../dart-core/int-class) index,
[Iterable](../dart-core/iterable-class)\<[Float32x4](float32x4-class)\>
iterable) → void

::: {.features}
inherited
:::

Overwrites elements with the objects of `iterable`.

[setRange](../dart-core/list/setrange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end,
[Iterable](../dart-core/iterable-class)\<[Float32x4](float32x4-class)\>
iterable, \[[int](../dart-core/int-class) skipCount = 0\]) → void

::: {.features}
inherited
:::

Writes some elements of `iterable` into a range of this list.

[shuffle](../dart-core/list/shuffle)(\[[Random](../dart-math/random-class)?
random\]) → void

::: {.features}
inherited
:::

Shuffles the elements of this list randomly.

[singleWhere](../dart-core/iterable/singlewhere)([bool](../dart-core/bool-class)
test([Float32x4](float32x4-class) element),
{[Float32x4](float32x4-class) orElse()?}) → [Float32x4](float32x4-class)

::: {.features}
inherited
:::

Returns the single element that satisfies `test`.

[skip](../dart-core/iterable/skip)([int](../dart-core/int-class) count)
→
[Iterable](../dart-core/iterable-class)\<[Float32x4](float32x4-class)\>

::: {.features}
inherited
:::

Returns an [Iterable](../dart-core/iterable-class) that provides all but
the first `count` elements.

[skipWhile](../dart-core/iterable/skipwhile)([bool](../dart-core/bool-class)
test([Float32x4](float32x4-class) value)) →
[Iterable](../dart-core/iterable-class)\<[Float32x4](float32x4-class)\>

::: {.features}
inherited
:::

Returns an `Iterable` that skips leading elements while `test` is
satisfied.

[sort](../dart-core/list/sort)(\[[int](../dart-core/int-class)
compare([Float32x4](float32x4-class) a, [Float32x4](float32x4-class)
b)?\]) → void

::: {.features}
inherited
:::

Sorts this list according to the order specified by the `compare`
function.

[sublist](float32x4list/sublist)([int](../dart-core/int-class) start,
\[[int](../dart-core/int-class)? end\]) →
[Float32x4List](float32x4list-class)

::: {.features}
override
:::

Returns a new list containing the elements between `start` and `end`.

[take](../dart-core/iterable/take)([int](../dart-core/int-class) count)
→
[Iterable](../dart-core/iterable-class)\<[Float32x4](float32x4-class)\>

::: {.features}
inherited
:::

Returns a lazy iterable of the `count` first elements of this iterable.

[takeWhile](../dart-core/iterable/takewhile)([bool](../dart-core/bool-class)
test([Float32x4](float32x4-class) value)) →
[Iterable](../dart-core/iterable-class)\<[Float32x4](float32x4-class)\>

::: {.features}
inherited
:::

Returns a lazy iterable of the leading elements satisfying `test`.

[toList](../dart-core/iterable/tolist)({[bool](../dart-core/bool-class)
growable = true}) →
[List](../dart-core/list-class)\<[Float32x4](float32x4-class)\>

::: {.features}
inherited
:::

Creates a [List](../dart-core/list-class) containing the elements of
this [Iterable](../dart-core/iterable-class).

[toSet](../dart-core/iterable/toset)() →
[Set](../dart-core/set-class)\<[Float32x4](float32x4-class)\>

::: {.features}
inherited
:::

Creates a [Set](../dart-core/set-class) containing the same elements as
this iterable.

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[where](../dart-core/iterable/where)([bool](../dart-core/bool-class)
test([Float32x4](float32x4-class) element)) →
[Iterable](../dart-core/iterable-class)\<[Float32x4](float32x4-class)\>

::: {.features}
inherited
:::

Returns a new lazy [Iterable](../dart-core/iterable-class) with all
elements that satisfy the predicate `test`.

[whereType](../dart-core/iterable/wheretype)\<T\>() →
[Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
inherited
:::

Returns a new lazy [Iterable](../dart-core/iterable-class) with all
elements that have type `T`.

Operators
---------

[operator
+](float32x4list/operator_plus)([List](../dart-core/list-class)\<[Float32x4](float32x4-class)\>
other) → [List](../dart-core/list-class)\<[Float32x4](float32x4-class)\>

::: {.features}
override
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
\[\]](../dart-core/list/operator_get)([int](../dart-core/int-class)
index) → [Float32x4](float32x4-class)

::: {.features}
inherited
:::

The object at the given `index` in the list.

[operator
\[\]=](../dart-core/list/operator_put)([int](../dart-core/int-class)
index, [Float32x4](float32x4-class) value) → void

::: {.features}
inherited
:::

Sets the value at the given `index` in the list to `value`.

Constants
---------

[bytesPerElement](float32x4list/bytesperelement-constant) → const [int](../dart-core/int-class)

:   <div>

    `16`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/Float32x4List-class.html>
:::

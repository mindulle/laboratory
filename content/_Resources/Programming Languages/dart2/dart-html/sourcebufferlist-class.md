[dart:html](../dart-html/dart-html-library){._links-link}

SourceBufferList class
======================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [EventTarget](eventtarget-class)
    -   SourceBufferList

Implemented types

:   -   [List](../dart-core/list-class)\<[SourceBuffer](sourcebuffer-class)\>

Mixed in types

:   -   [ListMixin](../dart-collection/listmixin-class)\<[SourceBuffer](sourcebuffer-class)\>
    -   [ImmutableListMixin](immutablelistmixin-class)\<[SourceBuffer](sourcebuffer-class)\>

Available Extensions

:   -   [EnumByName](../dart-core/enumbyname)

Annotations

:   -   \@Native(\"SourceBufferList\")

Properties {#instance-properties}
----------

[first](sourcebufferlist/first) ↔ [SourceBuffer](sourcebuffer-class)

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

[iterator](immutablelistmixin/iterator) →
[Iterator](../dart-core/iterator-class)\<[SourceBuffer](sourcebuffer-class)\>

::: {.features}
read-only, inherited
:::

Returns a new `Iterator` that allows iterating the elements of this
`Iterable`.

[last](sourcebufferlist/last) ↔ [SourceBuffer](sourcebuffer-class)

::: {.features}
read / write, inherited-setter, override-getter
:::

Returns the last element.

[length](sourcebufferlist/length) ↔ [int](../dart-core/int-class)

::: {.features}
read / write, override
:::

The number of objects in this list.

[on](eventtarget/on) → [Events](events-class)

::: {.features}
read-only, inherited
:::

This is an ease-of-use accessor for event streams which should only be
used when an explicit accessor is not available.

[reversed](../dart-collection/listmixin/reversed) →
[Iterable](../dart-core/iterable-class)\<[SourceBuffer](sourcebuffer-class)\>

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

[single](sourcebufferlist/single) → [SourceBuffer](sourcebuffer-class)

::: {.features}
read-only, override
:::

Checks that this iterable has only one element, and returns that
element.

Methods {#instance-methods}
-------

[add](immutablelistmixin/add)([SourceBuffer](sourcebuffer-class) value)
→ void

::: {.features}
inherited
:::

Adds `value` to the end of this list, extending the length by one.

[addAll](immutablelistmixin/addall)([Iterable](../dart-core/iterable-class)\<[SourceBuffer](sourcebuffer-class)\>
iterable) → void

::: {.features}
inherited
:::

Appends all objects of `iterable` to the end of this list.

[addEventListener](eventtarget/addeventlistener)([String](../dart-core/string-class)
type, [EventListener](eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[any](../dart-collection/listmixin/any)([bool](../dart-core/bool-class)
test([SourceBuffer](sourcebuffer-class) element)) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Checks whether any element of this iterable satisfies `test`.

[asMap](../dart-collection/listmixin/asmap)() →
[Map](../dart-core/map-class)\<[int](../dart-core/int-class),
[SourceBuffer](sourcebuffer-class)\>

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

[clear](../dart-collection/listmixin/clear)() → void

::: {.features}
inherited
:::

Removes all objects from this list; the length of the list becomes zero.

[contains](../dart-collection/listmixin/contains)([Object](../dart-core/object-class)?
element) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Whether the collection contains an element equal to `element`.

[dispatchEvent](eventtarget/dispatchevent)([Event](event-class) event) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

[elementAt](sourcebufferlist/elementat)([int](../dart-core/int-class)
index) → [SourceBuffer](sourcebuffer-class)

::: {.features}
override
:::

Returns the `index`th element.

[every](../dart-collection/listmixin/every)([bool](../dart-core/bool-class)
test([SourceBuffer](sourcebuffer-class) element)) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Checks whether every element of this iterable satisfies `test`.

[expand](../dart-collection/listmixin/expand)\<T\>([Iterable](../dart-core/iterable-class)\<T\>
f([SourceBuffer](sourcebuffer-class) element)) →
[Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
inherited
:::

Expands each element of this [Iterable](../dart-core/iterable-class)
into zero or more elements.

[fillRange](immutablelistmixin/fillrange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end,
\[[SourceBuffer](sourcebuffer-class)? fillValue\]) → void

::: {.features}
inherited
:::

Overwrites a range of elements with `fillValue`.

[firstWhere](../dart-collection/listmixin/firstwhere)([bool](../dart-core/bool-class)
test([SourceBuffer](sourcebuffer-class) element),
{[SourceBuffer](sourcebuffer-class) orElse()?}) →
[SourceBuffer](sourcebuffer-class)

::: {.features}
inherited
:::

Returns the first element that satisfies the given predicate `test`.

[fold](../dart-collection/listmixin/fold)\<T\>(T initialValue, T
combine(T previousValue, [SourceBuffer](sourcebuffer-class) element)) →
T

::: {.features}
inherited
:::

Reduces a collection to a single value by iteratively combining each
element of the collection with an existing value

[followedBy](../dart-collection/listmixin/followedby)([Iterable](../dart-core/iterable-class)\<[SourceBuffer](sourcebuffer-class)\>
other) →
[Iterable](../dart-core/iterable-class)\<[SourceBuffer](sourcebuffer-class)\>

::: {.features}
inherited
:::

Returns the lazy concatenation of this iterable and `other`.

[forEach](../dart-collection/listmixin/foreach)(void
action([SourceBuffer](sourcebuffer-class) element)) → void

::: {.features}
inherited
:::

Invokes `action` on each element of this iterable in iteration order.

[getRange](../dart-collection/listmixin/getrange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end) →
[Iterable](../dart-core/iterable-class)\<[SourceBuffer](sourcebuffer-class)\>

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
test([SourceBuffer](sourcebuffer-class) element),
\[[int](../dart-core/int-class) start = 0\]) →
[int](../dart-core/int-class)

::: {.features}
inherited
:::

The first index in the list that satisfies the provided `test`.

[insert](immutablelistmixin/insert)([int](../dart-core/int-class) index,
[SourceBuffer](sourcebuffer-class) element) → void

::: {.features}
inherited
:::

Inserts `element` at position `index` in this list.

[insertAll](immutablelistmixin/insertall)([int](../dart-core/int-class)
index,
[Iterable](../dart-core/iterable-class)\<[SourceBuffer](sourcebuffer-class)\>
iterable) → void

::: {.features}
inherited
:::

Inserts all objects of `iterable` at position `index` in this list.

[item](sourcebufferlist/item)([int](../dart-core/int-class) index) →
[SourceBuffer](sourcebuffer-class)

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
test([SourceBuffer](sourcebuffer-class) element),
\[[int](../dart-core/int-class)? start\]) →
[int](../dart-core/int-class)

::: {.features}
inherited
:::

The last index in the list that satisfies the provided `test`.

[lastWhere](../dart-collection/listmixin/lastwhere)([bool](../dart-core/bool-class)
test([SourceBuffer](sourcebuffer-class) element),
{[SourceBuffer](sourcebuffer-class) orElse()?}) →
[SourceBuffer](sourcebuffer-class)

::: {.features}
inherited
:::

Returns the last element that satisfies the given predicate `test`.

[map](../dart-collection/listmixin/map)\<T\>(T
f([SourceBuffer](sourcebuffer-class) element)) →
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

[reduce](../dart-collection/listmixin/reduce)([SourceBuffer](sourcebuffer-class)
combine([SourceBuffer](sourcebuffer-class) previousValue,
[SourceBuffer](sourcebuffer-class) element)) →
[SourceBuffer](sourcebuffer-class)

::: {.features}
inherited
:::

Reduces a collection to a single value by iteratively combining elements
of the collection using the provided function.

[remove](immutablelistmixin/remove)([Object](../dart-core/object-class)?
object) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Removes the first occurrence of `value` from this list.

[removeAt](immutablelistmixin/removeat)([int](../dart-core/int-class)
pos) → [SourceBuffer](sourcebuffer-class)

::: {.features}
inherited
:::

Removes the object at position `index` from this list.

[removeEventListener](eventtarget/removeeventlistener)([String](../dart-core/string-class)
type, [EventListener](eventlistener)? listener,
\[[bool](../dart-core/bool-class)? useCapture\]) → void

::: {.features}
inherited
:::

[removeLast](immutablelistmixin/removelast)() →
[SourceBuffer](sourcebuffer-class)

::: {.features}
inherited
:::

Removes and returns the last object in this list.

[removeRange](immutablelistmixin/removerange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end) → void

::: {.features}
inherited
:::

Removes a range of elements from the list.

[removeWhere](immutablelistmixin/removewhere)([bool](../dart-core/bool-class)
test([SourceBuffer](sourcebuffer-class) element)) → void

::: {.features}
inherited
:::

Removes all objects from this list that satisfy `test`.

[replaceRange](immutablelistmixin/replacerange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end,
[Iterable](../dart-core/iterable-class)\<[SourceBuffer](sourcebuffer-class)\>
iterable) → void

::: {.features}
inherited
:::

Replaces a range of elements with the elements of `replacements`.

[retainWhere](immutablelistmixin/retainwhere)([bool](../dart-core/bool-class)
test([SourceBuffer](sourcebuffer-class) element)) → void

::: {.features}
inherited
:::

Removes all objects from this list that fail to satisfy `test`.

[setAll](immutablelistmixin/setall)([int](../dart-core/int-class) index,
[Iterable](../dart-core/iterable-class)\<[SourceBuffer](sourcebuffer-class)\>
iterable) → void

::: {.features}
inherited
:::

Overwrites elements with the objects of `iterable`.

[setRange](immutablelistmixin/setrange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end,
[Iterable](../dart-core/iterable-class)\<[SourceBuffer](sourcebuffer-class)\>
iterable, \[[int](../dart-core/int-class) skipCount = 0\]) → void

::: {.features}
inherited
:::

Writes some elements of `iterable` into a range of this list.

[shuffle](immutablelistmixin/shuffle)(\[[Random](../dart-math/random-class)?
random\]) → void

::: {.features}
inherited
:::

Shuffles the elements of this list randomly.

[singleWhere](../dart-collection/listmixin/singlewhere)([bool](../dart-core/bool-class)
test([SourceBuffer](sourcebuffer-class) element),
{[SourceBuffer](sourcebuffer-class) orElse()?}) →
[SourceBuffer](sourcebuffer-class)

::: {.features}
inherited
:::

Returns the single element that satisfies `test`.

[skip](../dart-collection/listmixin/skip)([int](../dart-core/int-class)
count) →
[Iterable](../dart-core/iterable-class)\<[SourceBuffer](sourcebuffer-class)\>

::: {.features}
inherited
:::

Returns an [Iterable](../dart-core/iterable-class) that provides all but
the first `count` elements.

[skipWhile](../dart-collection/listmixin/skipwhile)([bool](../dart-core/bool-class)
test([SourceBuffer](sourcebuffer-class) element)) →
[Iterable](../dart-core/iterable-class)\<[SourceBuffer](sourcebuffer-class)\>

::: {.features}
inherited
:::

Returns an `Iterable` that skips leading elements while `test` is
satisfied.

[sort](immutablelistmixin/sort)(\[[int](../dart-core/int-class)
compare([SourceBuffer](sourcebuffer-class) a,
[SourceBuffer](sourcebuffer-class) b)?\]) → void

::: {.features}
inherited
:::

Sorts this list according to the order specified by the `compare`
function.

[sublist](../dart-collection/listmixin/sublist)([int](../dart-core/int-class)
start, \[[int](../dart-core/int-class)? end\]) →
[List](../dart-core/list-class)\<[SourceBuffer](sourcebuffer-class)\>

::: {.features}
inherited
:::

Returns a new list containing the elements between `start` and `end`.

[take](../dart-collection/listmixin/take)([int](../dart-core/int-class)
count) →
[Iterable](../dart-core/iterable-class)\<[SourceBuffer](sourcebuffer-class)\>

::: {.features}
inherited
:::

Returns a lazy iterable of the `count` first elements of this iterable.

[takeWhile](../dart-collection/listmixin/takewhile)([bool](../dart-core/bool-class)
test([SourceBuffer](sourcebuffer-class) element)) →
[Iterable](../dart-core/iterable-class)\<[SourceBuffer](sourcebuffer-class)\>

::: {.features}
inherited
:::

Returns a lazy iterable of the leading elements satisfying `test`.

[toList](../dart-collection/listmixin/tolist)({[bool](../dart-core/bool-class)
growable = true}) →
[List](../dart-core/list-class)\<[SourceBuffer](sourcebuffer-class)\>

::: {.features}
inherited
:::

Creates a [List](../dart-core/list-class) containing the elements of
this [Iterable](../dart-core/iterable-class).

[toSet](../dart-collection/listmixin/toset)() →
[Set](../dart-core/set-class)\<[SourceBuffer](sourcebuffer-class)\>

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
test([SourceBuffer](sourcebuffer-class) element)) →
[Iterable](../dart-core/iterable-class)\<[SourceBuffer](sourcebuffer-class)\>

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
+](../dart-collection/listmixin/operator_plus)([List](../dart-core/list-class)\<[SourceBuffer](sourcebuffer-class)\>
other) →
[List](../dart-core/list-class)\<[SourceBuffer](sourcebuffer-class)\>

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
\[\]](sourcebufferlist/operator_get)([int](../dart-core/int-class)
index) → [SourceBuffer](sourcebuffer-class)

::: {.features}
override
:::

The object at the given `index` in the list.

[operator
\[\]=](sourcebufferlist/operator_put)([int](../dart-core/int-class)
index, [SourceBuffer](sourcebuffer-class) value) → void

::: {.features}
override
:::

Sets the value at the given `index` in the list to `value`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/SourceBufferList-class.html>
:::

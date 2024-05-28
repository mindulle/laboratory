[dart:js](../dart-js/dart-js-library){._links-link}

JsArray\<E\> class
==================

A [List](../dart-core/list-class) that proxies a JavaScript array.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [JsObject](jsobject-class)
    -   JsArray

Mixed in types

:   -   [ListMixin](../dart-collection/listmixin-class)\<E\>

Available Extensions

:   -   [EnumByName](../dart-core/enumbyname)

Constructors
------------

[JsArray](jsarray/jsarray)()

::: {.constructor-modifier .features}
factory
:::

Creates an empty JavaScript array.

[JsArray.from](jsarray/jsarray.from)([Iterable](../dart-core/iterable-class)\<E\>
other)

::: {.constructor-modifier .features}
factory
:::

Creates a new JavaScript array and initializes it to the contents of
`other`.

Properties {#instance-properties}
----------

[first](../dart-collection/listmixin/first) ↔ E

::: {.features}
read / write, inherited
:::

Returns the first element.

[hashCode](jsobject/hashcode) → [int](../dart-core/int-class)

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
[Iterator](../dart-core/iterator-class)\<E\>

::: {.features}
read-only, inherited
:::

Returns a new `Iterator` that allows iterating the elements of this
`Iterable`.

[last](../dart-collection/listmixin/last) ↔ E

::: {.features}
read / write, inherited
:::

Returns the last element.

[length](jsarray/length) ↔ [int](../dart-core/int-class)

::: {.features}
read / write, override
:::

The number of objects in this list.

[reversed](../dart-collection/listmixin/reversed) →
[Iterable](../dart-core/iterable-class)\<E\>

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

[single](../dart-collection/listmixin/single) → E

::: {.features}
read-only, inherited
:::

Checks that this iterable has only one element, and returns that
element.

Methods {#instance-methods}
-------

[add](jsarray/add)(E value) → void

::: {.features}
override
:::

Adds `value` to the end of this list, extending the length by one.

[addAll](jsarray/addall)([Iterable](../dart-core/iterable-class)\<E\>
iterable) → void

::: {.features}
override
:::

Appends all objects of `iterable` to the end of this list.

[any](../dart-collection/listmixin/any)([bool](../dart-core/bool-class)
test(E element)) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Checks whether any element of this iterable satisfies `test`.

[asMap](../dart-collection/listmixin/asmap)() →
[Map](../dart-core/map-class)\<[int](../dart-core/int-class), E\>

::: {.features}
inherited
:::

An unmodifiable [Map](../dart-core/map-class) view of this list.

[callMethod](jsobject/callmethod)([Object](../dart-core/object-class)
method, \[[List](../dart-core/list-class)? args\]) → dynamic

::: {.features}
inherited
:::

Calls `method` on the JavaScript object with the arguments `args` and
returns the result.

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

[deleteProperty](jsobject/deleteproperty)([Object](../dart-core/object-class)
property) → void

::: {.features}
inherited
:::

Removes `property` from the JavaScript object.

[elementAt](../dart-collection/listmixin/elementat)([int](../dart-core/int-class)
index) → E

::: {.features}
inherited
:::

Returns the `index`th element.

[every](../dart-collection/listmixin/every)([bool](../dart-core/bool-class)
test(E element)) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Checks whether every element of this iterable satisfies `test`.

[expand](../dart-collection/listmixin/expand)\<T\>([Iterable](../dart-core/iterable-class)\<T\>
f(E element)) → [Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
inherited
:::

Expands each element of this [Iterable](../dart-core/iterable-class)
into zero or more elements.

[fillRange](../dart-collection/listmixin/fillrange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end, \[E? fill\]) → void

::: {.features}
inherited
:::

Overwrites a range of elements with `fillValue`.

[firstWhere](../dart-collection/listmixin/firstwhere)([bool](../dart-core/bool-class)
test(E element), {E orElse()?}) → E

::: {.features}
inherited
:::

Returns the first element that satisfies the given predicate `test`.

[fold](../dart-collection/listmixin/fold)\<T\>(T initialValue, T
combine(T previousValue, E element)) → T

::: {.features}
inherited
:::

Reduces a collection to a single value by iteratively combining each
element of the collection with an existing value

[followedBy](../dart-collection/listmixin/followedby)([Iterable](../dart-core/iterable-class)\<E\>
other) → [Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
inherited
:::

Returns the lazy concatenation of this iterable and `other`.

[forEach](../dart-collection/listmixin/foreach)(void action(E element))
→ void

::: {.features}
inherited
:::

Invokes `action` on each element of this iterable in iteration order.

[getRange](../dart-collection/listmixin/getrange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end) →
[Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
inherited
:::

Creates an [Iterable](../dart-core/iterable-class) that iterates over a
range of elements.

[hasProperty](jsobject/hasproperty)([Object](../dart-core/object-class)
property) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Returns `true` if the JavaScript object contains the specified property
either directly or though its prototype chain.

[indexOf](../dart-collection/listmixin/indexof)([Object](../dart-core/object-class)?
element, \[[int](../dart-core/int-class) start = 0\]) →
[int](../dart-core/int-class)

::: {.features}
inherited
:::

The first index of `element` in this list.

[indexWhere](../dart-collection/listmixin/indexwhere)([bool](../dart-core/bool-class)
test(E element), \[[int](../dart-core/int-class) start = 0\]) →
[int](../dart-core/int-class)

::: {.features}
inherited
:::

The first index in the list that satisfies the provided `test`.

[insert](jsarray/insert)([int](../dart-core/int-class) index, E element)
→ void

::: {.features}
override
:::

Inserts `element` at position `index` in this list.

[insertAll](../dart-collection/listmixin/insertall)([int](../dart-core/int-class)
index, [Iterable](../dart-core/iterable-class)\<E\> iterable) → void

::: {.features}
inherited
:::

Inserts all objects of `iterable` at position `index` in this list.

[instanceof](jsobject/instanceof)([JsFunction](jsfunction-class) type) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Returns `true` if the JavaScript object has `type` in its prototype
chain.

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
test(E element), \[[int](../dart-core/int-class)? start\]) →
[int](../dart-core/int-class)

::: {.features}
inherited
:::

The last index in the list that satisfies the provided `test`.

[lastWhere](../dart-collection/listmixin/lastwhere)([bool](../dart-core/bool-class)
test(E element), {E orElse()?}) → E

::: {.features}
inherited
:::

Returns the last element that satisfies the given predicate `test`.

[map](../dart-collection/listmixin/map)\<T\>(T f(E element)) →
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

[reduce](../dart-collection/listmixin/reduce)(E combine(E previousValue,
E element)) → E

::: {.features}
inherited
:::

Reduces a collection to a single value by iteratively combining elements
of the collection using the provided function.

[remove](../dart-collection/listmixin/remove)([Object](../dart-core/object-class)?
element) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Removes the first occurrence of `value` from this list.

[removeAt](jsarray/removeat)([int](../dart-core/int-class) index) → E

::: {.features}
override
:::

Removes the object at position `index` from this list.

[removeLast](jsarray/removelast)() → E

::: {.features}
override
:::

Removes and returns the last object in this list.

[removeRange](jsarray/removerange)([int](../dart-core/int-class) start,
[int](../dart-core/int-class) end) → void

::: {.features}
override
:::

Removes a range of elements from the list.

[removeWhere](../dart-collection/listmixin/removewhere)([bool](../dart-core/bool-class)
test(E element)) → void

::: {.features}
inherited
:::

Removes all objects from this list that satisfy `test`.

[replaceRange](../dart-collection/listmixin/replacerange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end,
[Iterable](../dart-core/iterable-class)\<E\> newContents) → void

::: {.features}
inherited
:::

Replaces a range of elements with the elements of `replacements`.

[retainWhere](../dart-collection/listmixin/retainwhere)([bool](../dart-core/bool-class)
test(E element)) → void

::: {.features}
inherited
:::

Removes all objects from this list that fail to satisfy `test`.

[setAll](../dart-collection/listmixin/setall)([int](../dart-core/int-class)
index, [Iterable](../dart-core/iterable-class)\<E\> iterable) → void

::: {.features}
inherited
:::

Overwrites elements with the objects of `iterable`.

[setRange](jsarray/setrange)([int](../dart-core/int-class) start,
[int](../dart-core/int-class) end,
[Iterable](../dart-core/iterable-class)\<E\> iterable,
\[[int](../dart-core/int-class) skipCount = 0\]) → void

::: {.features}
override
:::

Writes some elements of `iterable` into a range of this list.

[shuffle](../dart-collection/listmixin/shuffle)(\[[Random](../dart-math/random-class)?
random\]) → void

::: {.features}
inherited
:::

Shuffles the elements of this list randomly.

[singleWhere](../dart-collection/listmixin/singlewhere)([bool](../dart-core/bool-class)
test(E element), {E orElse()?}) → E

::: {.features}
inherited
:::

Returns the single element that satisfies `test`.

[skip](../dart-collection/listmixin/skip)([int](../dart-core/int-class)
count) → [Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
inherited
:::

Returns an [Iterable](../dart-core/iterable-class) that provides all but
the first `count` elements.

[skipWhile](../dart-collection/listmixin/skipwhile)([bool](../dart-core/bool-class)
test(E element)) → [Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
inherited
:::

Returns an `Iterable` that skips leading elements while `test` is
satisfied.

[sort](jsarray/sort)(\[[int](../dart-core/int-class) compare(E a, E
b)?\]) → void

::: {.features}
override
:::

Sorts this list according to the order specified by the `compare`
function.

[sublist](../dart-collection/listmixin/sublist)([int](../dart-core/int-class)
start, \[[int](../dart-core/int-class)? end\]) →
[List](../dart-core/list-class)\<E\>

::: {.features}
inherited
:::

Returns a new list containing the elements between `start` and `end`.

[take](../dart-collection/listmixin/take)([int](../dart-core/int-class)
count) → [Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
inherited
:::

Returns a lazy iterable of the `count` first elements of this iterable.

[takeWhile](../dart-collection/listmixin/takewhile)([bool](../dart-core/bool-class)
test(E element)) → [Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
inherited
:::

Returns a lazy iterable of the leading elements satisfying `test`.

[toList](../dart-collection/listmixin/tolist)({[bool](../dart-core/bool-class)
growable = true}) → [List](../dart-core/list-class)\<E\>

::: {.features}
inherited
:::

Creates a [List](../dart-core/list-class) containing the elements of
this [Iterable](../dart-core/iterable-class).

[toSet](../dart-collection/listmixin/toset)() →
[Set](../dart-core/set-class)\<E\>

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
test(E element)) → [Iterable](../dart-core/iterable-class)\<E\>

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
+](../dart-collection/listmixin/operator_plus)([List](../dart-core/list-class)\<E\>
other) → [List](../dart-core/list-class)\<E\>

::: {.features}
inherited
:::

Returns the concatenation of this list and `other`.

[operator
==](jsobject/operator_equals)([Object](../dart-core/object-class) other)
→ [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

[operator
\[\]](jsarray/operator_get)([Object](../dart-core/object-class) index) →
E

::: {.features}
override
:::

Returns the value associated with `property` from the proxied JavaScript
object.

[operator
\[\]=](jsarray/operator_put)([Object](../dart-core/object-class) index,
E value) → void

::: {.features}
override
:::

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-js/JsArray-class.html>
:::

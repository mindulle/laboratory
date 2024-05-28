[dart:collection](../dart-collection/dart-collection-library){._links-link}

UnmodifiableListView\<E\> class
===============================

An unmodifiable [List](../dart-core/list-class) view of another List.

The source of the elements may be a [List](../dart-core/list-class) or
any [Iterable](../dart-core/iterable-class) with efficient
[Iterable.length](../dart-core/iterable/length) and
[Iterable.elementAt](../dart-core/iterable/elementat).

``` {.language-dart data-language="dart"}
final numbers = <int>[10, 20, 30];
final unmodifiableListView = UnmodifiableListView(numbers);

// Insert new elements into the original list.
numbers.addAll([40, 50]);
print(unmodifiableListView); // [10, 20, 30, 40, 50]

unmodifiableListView.remove(20); // Throws.
```

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [ListBase](listbase-class)\<E\>
    -   UnmodifiableListView

Available Extensions

:   -   [EnumByName](../dart-core/enumbyname)

Constructors
------------

[UnmodifiableListView](unmodifiablelistview/unmodifiablelistview)([Iterable](../dart-core/iterable-class)\<E\> source)
:   Creates an unmodifiable list backed by `source`.

Properties {#instance-properties}
----------

[first](listmixin/first) ↔ E

::: {.features}
read / write, inherited
:::

Returns the first element.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isEmpty](listmixin/isempty) → [bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Whether this collection has no elements.

[isNotEmpty](listmixin/isnotempty) → [bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Whether this collection has at least one element.

[iterator](listmixin/iterator) →
[Iterator](../dart-core/iterator-class)\<E\>

::: {.features}
read-only, inherited
:::

Returns a new `Iterator` that allows iterating the elements of this
`Iterable`.

[last](listmixin/last) ↔ E

::: {.features}
read / write, inherited
:::

Returns the last element.

[length](unmodifiablelistview/length) ↔ [int](../dart-core/int-class)

::: {.features}
read / write, inherited-setter, override-getter
:::

The number of objects in this list.

[reversed](listmixin/reversed) →
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

[single](listmixin/single) → E

::: {.features}
read-only, inherited
:::

Checks that this iterable has only one element, and returns that
element.

Methods {#instance-methods}
-------

[add](unmodifiablelistview/add)(E value) → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable list.

[addAll](unmodifiablelistview/addall)([Iterable](../dart-core/iterable-class)\<E\>
iterable) → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable list.

[any](listmixin/any)([bool](../dart-core/bool-class) test(E element)) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Checks whether any element of this iterable satisfies `test`.

[asMap](listmixin/asmap)() →
[Map](../dart-core/map-class)\<[int](../dart-core/int-class), E\>

::: {.features}
inherited
:::

An unmodifiable [Map](../dart-core/map-class) view of this list.

[cast](unmodifiablelistview/cast)\<R\>() →
[List](../dart-core/list-class)\<R\>

::: {.features}
override
:::

Returns a view of this list as a list of `R` instances.

[clear](unmodifiablelistview/clear)() → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable list.

[contains](listmixin/contains)([Object](../dart-core/object-class)?
element) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Whether the collection contains an element equal to `element`.

[elementAt](listmixin/elementat)([int](../dart-core/int-class) index) →
E

::: {.features}
inherited
:::

Returns the `index`th element.

[every](listmixin/every)([bool](../dart-core/bool-class) test(E
element)) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Checks whether every element of this iterable satisfies `test`.

[expand](listmixin/expand)\<T\>([Iterable](../dart-core/iterable-class)\<T\>
f(E element)) → [Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
inherited
:::

Expands each element of this [Iterable](../dart-core/iterable-class)
into zero or more elements.

[fillRange](unmodifiablelistview/fillrange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end, \[E? fillValue\]) → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable list.

[firstWhere](listmixin/firstwhere)([bool](../dart-core/bool-class)
test(E element), {E orElse()?}) → E

::: {.features}
inherited
:::

Returns the first element that satisfies the given predicate `test`.

[fold](listmixin/fold)\<T\>(T initialValue, T combine(T previousValue, E
element)) → T

::: {.features}
inherited
:::

Reduces a collection to a single value by iteratively combining each
element of the collection with an existing value

[followedBy](listmixin/followedby)([Iterable](../dart-core/iterable-class)\<E\>
other) → [Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
inherited
:::

Returns the lazy concatenation of this iterable and `other`.

[forEach](listmixin/foreach)(void action(E element)) → void

::: {.features}
inherited
:::

Invokes `action` on each element of this iterable in iteration order.

[getRange](listmixin/getrange)([int](../dart-core/int-class) start,
[int](../dart-core/int-class) end) →
[Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
inherited
:::

Creates an [Iterable](../dart-core/iterable-class) that iterates over a
range of elements.

[indexOf](listmixin/indexof)([Object](../dart-core/object-class)?
element, \[[int](../dart-core/int-class) start = 0\]) →
[int](../dart-core/int-class)

::: {.features}
inherited
:::

The first index of `element` in this list.

[indexWhere](listmixin/indexwhere)([bool](../dart-core/bool-class)
test(E element), \[[int](../dart-core/int-class) start = 0\]) →
[int](../dart-core/int-class)

::: {.features}
inherited
:::

The first index in the list that satisfies the provided `test`.

[insert](unmodifiablelistview/insert)([int](../dart-core/int-class)
index, E element) → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable list.

[insertAll](unmodifiablelistview/insertall)([int](../dart-core/int-class)
at, [Iterable](../dart-core/iterable-class)\<E\> iterable) → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable list.

[join](listmixin/join)(\[[String](../dart-core/string-class) separator =
\"\"\]) → [String](../dart-core/string-class)

::: {.features}
inherited
:::

Converts each element to a [String](../dart-core/string-class) and
concatenates the strings.

[lastIndexOf](listmixin/lastindexof)([Object](../dart-core/object-class)?
element, \[[int](../dart-core/int-class)? start\]) →
[int](../dart-core/int-class)

::: {.features}
inherited
:::

The last index of `element` in this list.

[lastIndexWhere](listmixin/lastindexwhere)([bool](../dart-core/bool-class)
test(E element), \[[int](../dart-core/int-class)? start\]) →
[int](../dart-core/int-class)

::: {.features}
inherited
:::

The last index in the list that satisfies the provided `test`.

[lastWhere](listmixin/lastwhere)([bool](../dart-core/bool-class) test(E
element), {E orElse()?}) → E

::: {.features}
inherited
:::

Returns the last element that satisfies the given predicate `test`.

[map](listmixin/map)\<T\>(T f(E element)) →
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

[reduce](listmixin/reduce)(E combine(E previousValue, E element)) → E

::: {.features}
inherited
:::

Reduces a collection to a single value by iteratively combining elements
of the collection using the provided function.

[remove](unmodifiablelistview/remove)([Object](../dart-core/object-class)?
element) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable list.

[removeAt](unmodifiablelistview/removeat)([int](../dart-core/int-class)
index) → E

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable list.

[removeLast](unmodifiablelistview/removelast)() → E

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable list.

[removeRange](unmodifiablelistview/removerange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end) → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable list.

[removeWhere](unmodifiablelistview/removewhere)([bool](../dart-core/bool-class)
test(E element)) → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable list.

[replaceRange](unmodifiablelistview/replacerange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end,
[Iterable](../dart-core/iterable-class)\<E\> iterable) → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable list.

[retainWhere](unmodifiablelistview/retainwhere)([bool](../dart-core/bool-class)
test(E element)) → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable list.

[setAll](unmodifiablelistview/setall)([int](../dart-core/int-class) at,
[Iterable](../dart-core/iterable-class)\<E\> iterable) → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable list.

[setRange](unmodifiablelistview/setrange)([int](../dart-core/int-class)
start, [int](../dart-core/int-class) end,
[Iterable](../dart-core/iterable-class)\<E\> iterable,
\[[int](../dart-core/int-class) skipCount = 0\]) → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable list.

[shuffle](unmodifiablelistview/shuffle)(\[[Random](../dart-math/random-class)?
random\]) → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable list.

[singleWhere](listmixin/singlewhere)([bool](../dart-core/bool-class)
test(E element), {E orElse()?}) → E

::: {.features}
inherited
:::

Returns the single element that satisfies `test`.

[skip](listmixin/skip)([int](../dart-core/int-class) count) →
[Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
inherited
:::

Returns an [Iterable](../dart-core/iterable-class) that provides all but
the first `count` elements.

[skipWhile](listmixin/skipwhile)([bool](../dart-core/bool-class) test(E
element)) → [Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
inherited
:::

Returns an `Iterable` that skips leading elements while `test` is
satisfied.

[sort](unmodifiablelistview/sort)(\[[Comparator](../dart-core/comparator)\<E\>?
compare\]) → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable list.

[sublist](listmixin/sublist)([int](../dart-core/int-class) start,
\[[int](../dart-core/int-class)? end\]) →
[List](../dart-core/list-class)\<E\>

::: {.features}
inherited
:::

Returns a new list containing the elements between `start` and `end`.

[take](listmixin/take)([int](../dart-core/int-class) count) →
[Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
inherited
:::

Returns a lazy iterable of the `count` first elements of this iterable.

[takeWhile](listmixin/takewhile)([bool](../dart-core/bool-class) test(E
element)) → [Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
inherited
:::

Returns a lazy iterable of the leading elements satisfying `test`.

[toList](listmixin/tolist)({[bool](../dart-core/bool-class) growable =
true}) → [List](../dart-core/list-class)\<E\>

::: {.features}
inherited
:::

Creates a [List](../dart-core/list-class) containing the elements of
this [Iterable](../dart-core/iterable-class).

[toSet](listmixin/toset)() → [Set](../dart-core/set-class)\<E\>

::: {.features}
inherited
:::

Creates a [Set](../dart-core/set-class) containing the same elements as
this iterable.

[toString](listmixin/tostring)() → [String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[where](listmixin/where)([bool](../dart-core/bool-class) test(E
element)) → [Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
inherited
:::

Returns a new lazy [Iterable](../dart-core/iterable-class) with all
elements that satisfy the predicate `test`.

[whereType](listmixin/wheretype)\<T\>() →
[Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
inherited
:::

Returns a new lazy [Iterable](../dart-core/iterable-class) with all
elements that have type `T`.

Operators
---------

[operator
+](listmixin/operator_plus)([List](../dart-core/list-class)\<E\> other)
→ [List](../dart-core/list-class)\<E\>

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
\[\]](unmodifiablelistview/operator_get)([int](../dart-core/int-class)
index) → E

::: {.features}
override
:::

The object at the given `index` in the list.

[operator
\[\]=](unmodifiablelistview/operator_put)([int](../dart-core/int-class)
index, E value) → void

::: {.features}
inherited
:::

This operation is not supported by an unmodifiable list.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/UnmodifiableListView-class.html>
:::

[dart:collection](../dart-collection/dart-collection-library){._links-link}

SetBase\<E\> class
==================

Base implementation of [Set](../dart-core/set-class).

This class provides a base implementation of a `Set` that depends only
on the abstract members: [add](setmixin/add),
[contains](setmixin/contains), [lookup](setmixin/lookup),
[remove](setmixin/remove), [iterator](setmixin/iterator),
[length](setmixin/length) and [toSet](setmixin/toset).

Some of the methods assume that `toSet` creates a modifiable set. If
using this base class for an unmodifiable set, where `toSet` should
return an unmodifiable set, it\'s necessary to reimplement
[retainAll](setmixin/retainall), [union](setmixin/union),
[intersection](setmixin/intersection) and
[difference](setmixin/difference).

Implementations of `Set` using this base should consider also
implementing `clear` in constant time. The default implementation works
by removing every element.

Mixed in types

:   -   [SetMixin](setmixin-class)\<E\>

Implementers

:   -   [AttributeClassSet](../dart-svg/attributeclassset-class)
    -   [UnmodifiableSetView](unmodifiablesetview-class)

Available Extensions

:   -   [EnumByName](../dart-core/enumbyname)

Constructors
------------

[SetBase](setbase/setbase)()

Properties {#instance-properties}
----------

[first](setmixin/first) → E

::: {.features}
read-only, inherited
:::

Returns the first element.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isEmpty](setmixin/isempty) → [bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Whether this collection has no elements.

[isNotEmpty](setmixin/isnotempty) → [bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Whether this collection has at least one element.

[iterator](setmixin/iterator) →
[Iterator](../dart-core/iterator-class)\<E\>

::: {.features}
read-only, inherited
:::

An iterator that iterates over the elements of this set.

[last](setmixin/last) → E

::: {.features}
read-only, inherited
:::

Returns the last element.

[length](setmixin/length) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

Returns the number of elements in the iterable.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[single](setmixin/single) → E

::: {.features}
read-only, inherited
:::

Checks that this iterable has only one element, and returns that
element.

Methods {#instance-methods}
-------

[add](setmixin/add)(E value) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Adds `value` to the set.

[addAll](setmixin/addall)([Iterable](../dart-core/iterable-class)\<E\>
elements) → void

::: {.features}
inherited
:::

Adds all `elements` to this set.

[any](setmixin/any)([bool](../dart-core/bool-class) test(E element)) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Checks whether any element of this iterable satisfies `test`.

[cast](setmixin/cast)\<R\>() → [Set](../dart-core/set-class)\<R\>

::: {.features}
inherited
:::

Provides a view of this set as a set of `R` instances.

[clear](setmixin/clear)() → void

::: {.features}
inherited
:::

Removes all elements from the set.

[contains](setmixin/contains)([Object](../dart-core/object-class)?
element) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Whether `value` is in the set.

[containsAll](setmixin/containsall)([Iterable](../dart-core/iterable-class)\<[Object](../dart-core/object-class)?\>
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Whether this set contains all the elements of `other`.

[difference](setmixin/difference)([Set](../dart-core/set-class)\<[Object](../dart-core/object-class)?\>
other) → [Set](../dart-core/set-class)\<E\>

::: {.features}
inherited
:::

Creates a new set with the elements of this that are not in `other`.

[elementAt](setmixin/elementat)([int](../dart-core/int-class) index) → E

::: {.features}
inherited
:::

Returns the `index`th element.

[every](setmixin/every)([bool](../dart-core/bool-class) f(E element)) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Checks whether every element of this iterable satisfies `test`.

[expand](setmixin/expand)\<T\>([Iterable](../dart-core/iterable-class)\<T\>
f(E element)) → [Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
inherited
:::

Expands each element of this [Iterable](../dart-core/iterable-class)
into zero or more elements.

[firstWhere](setmixin/firstwhere)([bool](../dart-core/bool-class) test(E
value), {E orElse()?}) → E

::: {.features}
inherited
:::

Returns the first element that satisfies the given predicate `test`.

[fold](setmixin/fold)\<T\>(T initialValue, T combine(T previousValue, E
element)) → T

::: {.features}
inherited
:::

Reduces a collection to a single value by iteratively combining each
element of the collection with an existing value

[followedBy](setmixin/followedby)([Iterable](../dart-core/iterable-class)\<E\>
other) → [Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
inherited
:::

Returns the lazy concatenation of this iterable and `other`.

[forEach](setmixin/foreach)(void f(E element)) → void

::: {.features}
inherited
:::

Invokes `action` on each element of this iterable in iteration order.

[intersection](setmixin/intersection)([Set](../dart-core/set-class)\<[Object](../dart-core/object-class)?\>
other) → [Set](../dart-core/set-class)\<E\>

::: {.features}
inherited
:::

Creates a new set which is the intersection between this set and
`other`.

[join](setmixin/join)(\[[String](../dart-core/string-class) separator =
\"\"\]) → [String](../dart-core/string-class)

::: {.features}
inherited
:::

Converts each element to a [String](../dart-core/string-class) and
concatenates the strings.

[lastWhere](setmixin/lastwhere)([bool](../dart-core/bool-class) test(E
value), {E orElse()?}) → E

::: {.features}
inherited
:::

Returns the last element that satisfies the given predicate `test`.

[lookup](setmixin/lookup)([Object](../dart-core/object-class)? element)
→ E?

::: {.features}
inherited
:::

If an object equal to `object` is in the set, return it.

[map](setmixin/map)\<T\>(T f(E element)) →
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

[reduce](setmixin/reduce)(E combine(E value, E element)) → E

::: {.features}
inherited
:::

Reduces a collection to a single value by iteratively combining elements
of the collection using the provided function.

[remove](setmixin/remove)([Object](../dart-core/object-class)? value) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Removes `value` from the set.

[removeAll](setmixin/removeall)([Iterable](../dart-core/iterable-class)\<[Object](../dart-core/object-class)?\>
elements) → void

::: {.features}
inherited
:::

Removes each element of `elements` from this set.

[removeWhere](setmixin/removewhere)([bool](../dart-core/bool-class)
test(E element)) → void

::: {.features}
inherited
:::

Removes all elements of this set that satisfy `test`.

[retainAll](setmixin/retainall)([Iterable](../dart-core/iterable-class)\<[Object](../dart-core/object-class)?\>
elements) → void

::: {.features}
inherited
:::

Removes all elements of this set that are not elements in `elements`.

[retainWhere](setmixin/retainwhere)([bool](../dart-core/bool-class)
test(E element)) → void

::: {.features}
inherited
:::

Removes all elements of this set that fail to satisfy `test`.

[singleWhere](setmixin/singlewhere)([bool](../dart-core/bool-class)
test(E value), {E orElse()?}) → E

::: {.features}
inherited
:::

Returns the single element that satisfies `test`.

[skip](setmixin/skip)([int](../dart-core/int-class) n) →
[Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
inherited
:::

Returns an [Iterable](../dart-core/iterable-class) that provides all but
the first `count` elements.

[skipWhile](setmixin/skipwhile)([bool](../dart-core/bool-class) test(E
value)) → [Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
inherited
:::

Returns an `Iterable` that skips leading elements while `test` is
satisfied.

[take](setmixin/take)([int](../dart-core/int-class) n) →
[Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
inherited
:::

Returns a lazy iterable of the `count` first elements of this iterable.

[takeWhile](setmixin/takewhile)([bool](../dart-core/bool-class) test(E
value)) → [Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
inherited
:::

Returns a lazy iterable of the leading elements satisfying `test`.

[toList](setmixin/tolist)({[bool](../dart-core/bool-class) growable =
true}) → [List](../dart-core/list-class)\<E\>

::: {.features}
inherited
:::

Creates a [List](../dart-core/list-class) containing the elements of
this [Iterable](../dart-core/iterable-class).

[toSet](setmixin/toset)() → [Set](../dart-core/set-class)\<E\>

::: {.features}
inherited
:::

Creates a [Set](../dart-core/set-class) with the same elements and
behavior as this `Set`.

[toString](setmixin/tostring)() → [String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[union](setmixin/union)([Set](../dart-core/set-class)\<E\> other) →
[Set](../dart-core/set-class)\<E\>

::: {.features}
inherited
:::

Creates a new set which contains all the elements of this set and
`other`.

[where](setmixin/where)([bool](../dart-core/bool-class) f(E element)) →
[Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
inherited
:::

Returns a new lazy [Iterable](../dart-core/iterable-class) with all
elements that satisfy the predicate `test`.

[whereType](setmixin/wheretype)\<T\>() →
[Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
inherited
:::

Returns a new lazy [Iterable](../dart-core/iterable-class) with all
elements that have type `T`.

Operators
---------

[operator
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

Static Methods
--------------

[setToString](setbase/settostring)([Set](../dart-core/set-class) set) → [String](../dart-core/string-class)
:   Converts a [Set](../dart-core/set-class) to a
    [String](../dart-core/string-class).

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SetBase-class.html>
:::

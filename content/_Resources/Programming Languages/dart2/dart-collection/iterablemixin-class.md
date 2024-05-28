[dart:collection](../dart-collection/dart-collection-library){._links-link}

IterableMixin\<E\> class
========================

This [Iterable](../dart-core/iterable-class) mixin implements all
[Iterable](../dart-core/iterable-class) members except `iterator`.

All other methods are implemented in terms of `iterator`.

Implemented types

:   -   [Iterable](../dart-core/iterable-class)\<E\>

Implementers

:   -   [SplayTreeSet](splaytreeset-class)

Available Extensions

:   -   [EnumByName](../dart-core/enumbyname)

Constructors
------------

[IterableMixin](iterablemixin/iterablemixin)()

Properties {#instance-properties}
----------

[first](iterablemixin/first) → E

::: {.features}
read-only, override
:::

Returns the first element.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isEmpty](iterablemixin/isempty) → [bool](../dart-core/bool-class)

::: {.features}
read-only, override
:::

Whether this collection has no elements.

[isNotEmpty](iterablemixin/isnotempty) → [bool](../dart-core/bool-class)

::: {.features}
read-only, override
:::

Whether this collection has at least one element.

[iterator](../dart-core/iterable/iterator) →
[Iterator](../dart-core/iterator-class)\<E\>

::: {.features}
read-only, inherited
:::

Returns a new `Iterator` that allows iterating the elements of this
`Iterable`.

[last](iterablemixin/last) → E

::: {.features}
read-only, override
:::

Returns the last element.

[length](iterablemixin/length) → [int](../dart-core/int-class)

::: {.features}
read-only, override
:::

Returns the number of elements in [this](iterablemixin-class).

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[single](iterablemixin/single) → E

::: {.features}
read-only, override
:::

Checks that this iterable has only one element, and returns that
element.

Methods {#instance-methods}
-------

[any](iterablemixin/any)([bool](../dart-core/bool-class) test(E
element)) → [bool](../dart-core/bool-class)

::: {.features}
override
:::

Checks whether any element of this iterable satisfies `test`.

[cast](iterablemixin/cast)\<R\>() →
[Iterable](../dart-core/iterable-class)\<R\>

::: {.features}
override
:::

Provides a view of this iterable as an iterable of `R` instances.

[contains](iterablemixin/contains)([Object](../dart-core/object-class)?
element) → [bool](../dart-core/bool-class)

::: {.features}
override
:::

Whether the collection contains an element equal to `element`.

[elementAt](iterablemixin/elementat)([int](../dart-core/int-class)
index) → E

::: {.features}
override
:::

Returns the `index`th element.

[every](iterablemixin/every)([bool](../dart-core/bool-class) test(E
element)) → [bool](../dart-core/bool-class)

::: {.features}
override
:::

Checks whether every element of this iterable satisfies `test`.

[expand](iterablemixin/expand)\<T\>([Iterable](../dart-core/iterable-class)\<T\>
toElements(E element)) → [Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
override
:::

Expands each element of this [Iterable](../dart-core/iterable-class)
into zero or more elements.

[firstWhere](iterablemixin/firstwhere)([bool](../dart-core/bool-class)
test(E value), {E orElse()?}) → E

::: {.features}
override
:::

Returns the first element that satisfies the given predicate `test`.

[fold](iterablemixin/fold)\<T\>(T initialValue, T combine(T
previousValue, E element)) → T

::: {.features}
override
:::

Reduces a collection to a single value by iteratively combining each
element of the collection with an existing value

[followedBy](iterablemixin/followedby)([Iterable](../dart-core/iterable-class)\<E\>
other) → [Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
override
:::

Returns the lazy concatenation of this iterable and `other`.

[forEach](iterablemixin/foreach)(void action(E element)) → void

::: {.features}
override
:::

Invokes `action` on each element of this iterable in iteration order.

[join](iterablemixin/join)(\[[String](../dart-core/string-class)
separator = \"\"\]) → [String](../dart-core/string-class)

::: {.features}
override
:::

Converts each element to a [String](../dart-core/string-class) and
concatenates the strings.

[lastWhere](iterablemixin/lastwhere)([bool](../dart-core/bool-class)
test(E value), {E orElse()?}) → E

::: {.features}
override
:::

Returns the last element that satisfies the given predicate `test`.

[map](iterablemixin/map)\<T\>(T toElement(E element)) →
[Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
override
:::

The current elements of this iterable modified by `toElement`.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[reduce](iterablemixin/reduce)(E combine(E value, E element)) → E

::: {.features}
override
:::

Reduces a collection to a single value by iteratively combining elements
of the collection using the provided function.

[singleWhere](iterablemixin/singlewhere)([bool](../dart-core/bool-class)
test(E element), {E orElse()?}) → E

::: {.features}
override
:::

Returns the single element that satisfies `test`.

[skip](iterablemixin/skip)([int](../dart-core/int-class) count) →
[Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
override
:::

Returns an [Iterable](../dart-core/iterable-class) that provides all but
the first `count` elements.

[skipWhile](iterablemixin/skipwhile)([bool](../dart-core/bool-class)
test(E value)) → [Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
override
:::

Returns an `Iterable` that skips leading elements while `test` is
satisfied.

[take](iterablemixin/take)([int](../dart-core/int-class) count) →
[Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
override
:::

Returns a lazy iterable of the `count` first elements of this iterable.

[takeWhile](iterablemixin/takewhile)([bool](../dart-core/bool-class)
test(E value)) → [Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
override
:::

Returns a lazy iterable of the leading elements satisfying `test`.

[toList](iterablemixin/tolist)({[bool](../dart-core/bool-class) growable
= true}) → [List](../dart-core/list-class)\<E\>

::: {.features}
override
:::

Creates a [List](../dart-core/list-class) containing the elements of
this [Iterable](../dart-core/iterable-class).

[toSet](iterablemixin/toset)() → [Set](../dart-core/set-class)\<E\>

::: {.features}
override
:::

Creates a [Set](../dart-core/set-class) containing the same elements as
this iterable.

[toString](iterablemixin/tostring)() →
[String](../dart-core/string-class)

::: {.features}
override
:::

A string representation of this object.

[where](iterablemixin/where)([bool](../dart-core/bool-class) test(E
element)) → [Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
override
:::

Returns a new lazy [Iterable](../dart-core/iterable-class) with all
elements that satisfy the predicate `test`.

[whereType](iterablemixin/wheretype)\<T\>() →
[Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
override
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

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/IterableMixin-class.html>
:::

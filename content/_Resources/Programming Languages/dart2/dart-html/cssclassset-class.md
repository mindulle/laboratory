[dart:html](../dart-html/dart-html-library){._links-link}

CssClassSet class
=================

A Set that stores the CSS class names for an element.

Implemented types

:   -   [Set](../dart-core/set-class)\<[String](../dart-core/string-class)\>

Implementers

:   -   [AttributeClassSet](../dart-svg/attributeclassset-class)

Available Extensions

:   -   [EnumByName](../dart-core/enumbyname)

Constructors
------------

[CssClassSet](cssclassset/cssclassset)()

Properties {#instance-properties}
----------

[first](../dart-core/iterable/first) →
[String](../dart-core/string-class)

::: {.features}
read-only, inherited
:::

Returns the first element.

[frozen](cssclassset/frozen) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Returns `true` if classes cannot be added or removed from this
`CssClassSet`.

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

[iterator](../dart-core/set/iterator) →
[Iterator](../dart-core/iterator-class)\<[String](../dart-core/string-class)\>

::: {.features}
read-only, inherited
:::

An iterator that iterates over the elements of this set.

[last](../dart-core/iterable/last) → [String](../dart-core/string-class)

::: {.features}
read-only, inherited
:::

Returns the last element.

[length](cssclassset/length) → [int](../dart-core/int-class)

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

[single](../dart-core/iterable/single) →
[String](../dart-core/string-class)

::: {.features}
read-only, inherited
:::

Checks that this iterable has only one element, and returns that
element.

Methods {#instance-methods}
-------

[add](cssclassset/add)([String](../dart-core/string-class) value) →
[bool](../dart-core/bool-class)

::: {.features}
override
:::

Add the class `value` to element.

[addAll](cssclassset/addall)([Iterable](../dart-core/iterable-class)\<[String](../dart-core/string-class)\>
iterable) → void

::: {.features}
override
:::

Add all classes specified in `iterable` to element.

[any](../dart-core/iterable/any)([bool](../dart-core/bool-class)
test([String](../dart-core/string-class) element)) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Checks whether any element of this iterable satisfies `test`.

[cast](../dart-core/set/cast)\<R\>() →
[Set](../dart-core/set-class)\<R\>

::: {.features}
inherited
:::

Provides a view of this set as a set of `R` instances.

[clear](../dart-core/set/clear)() → void

::: {.features}
inherited
:::

Removes all elements from the set.

[contains](cssclassset/contains)([Object](../dart-core/object-class)?
value) → [bool](../dart-core/bool-class)

::: {.features}
override
:::

Determine if this element contains the class `value`.

[containsAll](../dart-core/set/containsall)([Iterable](../dart-core/iterable-class)\<[Object](../dart-core/object-class)?\>
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Whether this set contains all the elements of `other`.

[difference](../dart-core/set/difference)([Set](../dart-core/set-class)\<[Object](../dart-core/object-class)?\>
other) →
[Set](../dart-core/set-class)\<[String](../dart-core/string-class)\>

::: {.features}
inherited
:::

Creates a new set with the elements of this that are not in `other`.

[elementAt](../dart-core/iterable/elementat)([int](../dart-core/int-class)
index) → [String](../dart-core/string-class)

::: {.features}
inherited
:::

Returns the `index`th element.

[every](../dart-core/iterable/every)([bool](../dart-core/bool-class)
test([String](../dart-core/string-class) element)) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Checks whether every element of this iterable satisfies `test`.

[expand](../dart-core/iterable/expand)\<T\>([Iterable](../dart-core/iterable-class)\<T\>
toElements([String](../dart-core/string-class) element)) →
[Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
inherited
:::

Expands each element of this [Iterable](../dart-core/iterable-class)
into zero or more elements.

[firstWhere](../dart-core/iterable/firstwhere)([bool](../dart-core/bool-class)
test([String](../dart-core/string-class) element),
{[String](../dart-core/string-class) orElse()?}) →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

Returns the first element that satisfies the given predicate `test`.

[fold](../dart-core/iterable/fold)\<T\>(T initialValue, T combine(T
previousValue, [String](../dart-core/string-class) element)) → T

::: {.features}
inherited
:::

Reduces a collection to a single value by iteratively combining each
element of the collection with an existing value

[followedBy](../dart-core/iterable/followedby)([Iterable](../dart-core/iterable-class)\<[String](../dart-core/string-class)\>
other) →
[Iterable](../dart-core/iterable-class)\<[String](../dart-core/string-class)\>

::: {.features}
inherited
:::

Returns the lazy concatenation of this iterable and `other`.

[forEach](../dart-core/iterable/foreach)(void
action([String](../dart-core/string-class) element)) → void

::: {.features}
inherited
:::

Invokes `action` on each element of this iterable in iteration order.

[intersection](../dart-core/set/intersection)([Set](../dart-core/set-class)\<[Object](../dart-core/object-class)?\>
other) →
[Set](../dart-core/set-class)\<[String](../dart-core/string-class)\>

::: {.features}
inherited
:::

Creates a new set which is the intersection between this set and
`other`.

[join](../dart-core/iterable/join)(\[[String](../dart-core/string-class)
separator = \"\"\]) → [String](../dart-core/string-class)

::: {.features}
inherited
:::

Converts each element to a [String](../dart-core/string-class) and
concatenates the strings.

[lastWhere](../dart-core/iterable/lastwhere)([bool](../dart-core/bool-class)
test([String](../dart-core/string-class) element),
{[String](../dart-core/string-class) orElse()?}) →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

Returns the last element that satisfies the given predicate `test`.

[lookup](../dart-core/set/lookup)([Object](../dart-core/object-class)?
object) → [String](../dart-core/string-class)?

::: {.features}
inherited
:::

If an object equal to `object` is in the set, return it.

[map](../dart-core/iterable/map)\<T\>(T
toElement([String](../dart-core/string-class) e)) →
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

[reduce](../dart-core/iterable/reduce)([String](../dart-core/string-class)
combine([String](../dart-core/string-class) value,
[String](../dart-core/string-class) element)) →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

Reduces a collection to a single value by iteratively combining elements
of the collection using the provided function.

[remove](cssclassset/remove)([Object](../dart-core/object-class)? value)
→ [bool](../dart-core/bool-class)

::: {.features}
override
:::

Remove the class `value` from element, and return true on successful
removal.

[removeAll](cssclassset/removeall)([Iterable](../dart-core/iterable-class)\<[Object](../dart-core/object-class)?\>
iterable) → void

::: {.features}
override
:::

Remove all classes specified in `iterable` from element.

[removeWhere](../dart-core/set/removewhere)([bool](../dart-core/bool-class)
test([String](../dart-core/string-class) element)) → void

::: {.features}
inherited
:::

Removes all elements of this set that satisfy `test`.

[retainAll](../dart-core/set/retainall)([Iterable](../dart-core/iterable-class)\<[Object](../dart-core/object-class)?\>
elements) → void

::: {.features}
inherited
:::

Removes all elements of this set that are not elements in `elements`.

[retainWhere](../dart-core/set/retainwhere)([bool](../dart-core/bool-class)
test([String](../dart-core/string-class) element)) → void

::: {.features}
inherited
:::

Removes all elements of this set that fail to satisfy `test`.

[singleWhere](../dart-core/iterable/singlewhere)([bool](../dart-core/bool-class)
test([String](../dart-core/string-class) element),
{[String](../dart-core/string-class) orElse()?}) →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

Returns the single element that satisfies `test`.

[skip](../dart-core/iterable/skip)([int](../dart-core/int-class) count)
→
[Iterable](../dart-core/iterable-class)\<[String](../dart-core/string-class)\>

::: {.features}
inherited
:::

Returns an [Iterable](../dart-core/iterable-class) that provides all but
the first `count` elements.

[skipWhile](../dart-core/iterable/skipwhile)([bool](../dart-core/bool-class)
test([String](../dart-core/string-class) value)) →
[Iterable](../dart-core/iterable-class)\<[String](../dart-core/string-class)\>

::: {.features}
inherited
:::

Returns an `Iterable` that skips leading elements while `test` is
satisfied.

[take](../dart-core/iterable/take)([int](../dart-core/int-class) count)
→
[Iterable](../dart-core/iterable-class)\<[String](../dart-core/string-class)\>

::: {.features}
inherited
:::

Returns a lazy iterable of the `count` first elements of this iterable.

[takeWhile](../dart-core/iterable/takewhile)([bool](../dart-core/bool-class)
test([String](../dart-core/string-class) value)) →
[Iterable](../dart-core/iterable-class)\<[String](../dart-core/string-class)\>

::: {.features}
inherited
:::

Returns a lazy iterable of the leading elements satisfying `test`.

[toggle](cssclassset/toggle)([String](../dart-core/string-class) value,
\[[bool](../dart-core/bool-class)? shouldAdd\]) →
[bool](../dart-core/bool-class)

Adds the class `value` to the element if it is not on it, removes it if
it is.

[toggleAll](cssclassset/toggleall)([Iterable](../dart-core/iterable-class)\<[String](../dart-core/string-class)\>
iterable, \[[bool](../dart-core/bool-class)? shouldAdd\]) → void

Toggles all classes specified in `iterable` on element.

[toList](../dart-core/iterable/tolist)({[bool](../dart-core/bool-class)
growable = true}) →
[List](../dart-core/list-class)\<[String](../dart-core/string-class)\>

::: {.features}
inherited
:::

Creates a [List](../dart-core/list-class) containing the elements of
this [Iterable](../dart-core/iterable-class).

[toSet](../dart-core/set/toset)() →
[Set](../dart-core/set-class)\<[String](../dart-core/string-class)\>

::: {.features}
inherited
:::

Creates a [Set](../dart-core/set-class) with the same elements and
behavior as this `Set`.

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[union](../dart-core/set/union)([Set](../dart-core/set-class)\<[String](../dart-core/string-class)\>
other) →
[Set](../dart-core/set-class)\<[String](../dart-core/string-class)\>

::: {.features}
inherited
:::

Creates a new set which contains all the elements of this set and
`other`.

[where](../dart-core/iterable/where)([bool](../dart-core/bool-class)
test([String](../dart-core/string-class) element)) →
[Iterable](../dart-core/iterable-class)\<[String](../dart-core/string-class)\>

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
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssClassSet-class.html>
:::

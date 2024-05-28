[dart:svg](../dart-svg/dart-svg-library){._links-link}

AttributeClassSet class
=======================

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [SetBase](../dart-collection/setbase-class)\<[String](../dart-core/string-class)\>
    -   AttributeClassSet

Available Extensions

:   -   [EnumByName](../dart-core/enumbyname)

Constructors
------------

[AttributeClassSet](attributeclassset/attributeclassset)([Element](../dart-html/element-class)
\_element)

Properties {#instance-properties}
----------

[first](attributeclassset/first) → [String](../dart-core/string-class)

::: {.features}
read-only, inherited
:::

Returns the first element.

[frozen](attributeclassset/frozen) → [bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Returns `true` if classes cannot be added or removed from this
`CssClassSet`.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isEmpty](attributeclassset/isempty) → [bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Whether this collection has no elements.

[isNotEmpty](attributeclassset/isnotempty) →
[bool](../dart-core/bool-class)

::: {.features}
read-only, inherited
:::

Whether this collection has at least one element.

[iterator](attributeclassset/iterator) →
[Iterator](../dart-core/iterator-class)\<[String](../dart-core/string-class)\>

::: {.features}
read-only, inherited
:::

An iterator that iterates over the elements of this set.

[last](attributeclassset/last) → [String](../dart-core/string-class)

::: {.features}
read-only, inherited
:::

Returns the last element.

[length](attributeclassset/length) → [int](../dart-core/int-class)

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

[single](attributeclassset/single) → [String](../dart-core/string-class)

::: {.features}
read-only, inherited
:::

Checks that this iterable has only one element, and returns that
element.

Methods {#instance-methods}
-------

[add](attributeclassset/add)([String](../dart-core/string-class) value)
→ [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Add the class `value` to element.

[addAll](attributeclassset/addall)([Iterable](../dart-core/iterable-class)\<[String](../dart-core/string-class)\>
iterable) → void

::: {.features}
inherited
:::

Add all classes specified in `iterable` to element.

[any](attributeclassset/any)([bool](../dart-core/bool-class)
f([String](../dart-core/string-class) element)) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Checks whether any element of this iterable satisfies `test`.

[cast](../dart-collection/setmixin/cast)\<R\>() →
[Set](../dart-core/set-class)\<R\>

::: {.features}
inherited
:::

Provides a view of this set as a set of `R` instances.

[clear](attributeclassset/clear)() → void

::: {.features}
inherited
:::

Removes all elements from the set.

[contains](attributeclassset/contains)([Object](../dart-core/object-class)?
value) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Determine if this element contains the class `value`.

[containsAll](attributeclassset/containsall)([Iterable](../dart-core/iterable-class)\<[Object](../dart-core/object-class)?\>
collection) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Whether this set contains all the elements of `other`.

[difference](attributeclassset/difference)([Set](../dart-core/set-class)\<[Object](../dart-core/object-class)?\>
other) →
[Set](../dart-core/set-class)\<[String](../dart-core/string-class)\>

::: {.features}
inherited
:::

Creates a new set with the elements of this that are not in `other`.

[elementAt](attributeclassset/elementat)([int](../dart-core/int-class)
index) → [String](../dart-core/string-class)

::: {.features}
inherited
:::

Returns the `index`th element.

[every](attributeclassset/every)([bool](../dart-core/bool-class)
f([String](../dart-core/string-class) element)) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Checks whether every element of this iterable satisfies `test`.

[expand](attributeclassset/expand)\<T\>([Iterable](../dart-core/iterable-class)\<T\>
f([String](../dart-core/string-class) element)) →
[Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
inherited
:::

Expands each element of this [Iterable](../dart-core/iterable-class)
into zero or more elements.

[firstWhere](attributeclassset/firstwhere)([bool](../dart-core/bool-class)
test([String](../dart-core/string-class) value),
{[String](../dart-core/string-class) orElse()?}) →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

Returns the first element that satisfies the given predicate `test`.

[fold](attributeclassset/fold)\<T\>(T initialValue, T combine(T
previousValue, [String](../dart-core/string-class) element)) → T

::: {.features}
inherited
:::

Reduces a collection to a single value by iteratively combining each
element of the collection with an existing value

[followedBy](../dart-collection/setmixin/followedby)([Iterable](../dart-core/iterable-class)\<[String](../dart-core/string-class)\>
other) →
[Iterable](../dart-core/iterable-class)\<[String](../dart-core/string-class)\>

::: {.features}
inherited
:::

Returns the lazy concatenation of this iterable and `other`.

[forEach](attributeclassset/foreach)(void
f([String](../dart-core/string-class) element)) → void

::: {.features}
inherited
:::

Invokes `action` on each element of this iterable in iteration order.

[intersection](attributeclassset/intersection)([Set](../dart-core/set-class)\<[Object](../dart-core/object-class)?\>
other) →
[Set](../dart-core/set-class)\<[String](../dart-core/string-class)\>

::: {.features}
inherited
:::

Creates a new set which is the intersection between this set and
`other`.

[join](attributeclassset/join)(\[[String](../dart-core/string-class)
separator = \"\"\]) → [String](../dart-core/string-class)

::: {.features}
inherited
:::

Converts each element to a [String](../dart-core/string-class) and
concatenates the strings.

[lastWhere](attributeclassset/lastwhere)([bool](../dart-core/bool-class)
test([String](../dart-core/string-class) value),
{[String](../dart-core/string-class) orElse()?}) →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

Returns the last element that satisfies the given predicate `test`.

[lookup](attributeclassset/lookup)([Object](../dart-core/object-class)?
value) → [String](../dart-core/string-class)?

::: {.features}
inherited
:::

Lookup from the Set interface. Not interesting for a String set.

[map](attributeclassset/map)\<T\>(T
f([String](../dart-core/string-class) e)) →
[Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
inherited
:::

The current elements of this iterable modified by `toElement`.

[modify](attributeclassset/modify)(dynamic
f([Set](../dart-core/set-class)\<[String](../dart-core/string-class)\>
s)) → dynamic

::: {.features}
inherited
:::

Helper method used to modify the set of css classes on this element.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[readClasses](attributeclassset/readclasses)() →
[Set](../dart-core/set-class)\<[String](../dart-core/string-class)\>

Read the class names from the Element class property, and put them into
a set (duplicates are discarded). This is intended to be overridden by
specific implementations.

[reduce](attributeclassset/reduce)([String](../dart-core/string-class)
combine([String](../dart-core/string-class) value,
[String](../dart-core/string-class) element)) →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

Reduces a collection to a single value by iteratively combining elements
of the collection using the provided function.

[remove](attributeclassset/remove)([Object](../dart-core/object-class)?
value) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Remove the class `value` from element, and return true on successful
removal.

[removeAll](attributeclassset/removeall)([Iterable](../dart-core/iterable-class)\<[Object](../dart-core/object-class)?\>
iterable) → void

::: {.features}
inherited
:::

Remove all classes specified in `iterable` from element.

[removeWhere](attributeclassset/removewhere)([bool](../dart-core/bool-class)
test([String](../dart-core/string-class) name)) → void

::: {.features}
inherited
:::

Removes all elements of this set that satisfy `test`.

[retainAll](attributeclassset/retainall)([Iterable](../dart-core/iterable-class)\<[Object](../dart-core/object-class)?\>
iterable) → void

::: {.features}
inherited
:::

Removes all elements of this set that are not elements in `elements`.

[retainWhere](attributeclassset/retainwhere)([bool](../dart-core/bool-class)
test([String](../dart-core/string-class) name)) → void

::: {.features}
inherited
:::

Removes all elements of this set that fail to satisfy `test`.

[singleWhere](attributeclassset/singlewhere)([bool](../dart-core/bool-class)
test([String](../dart-core/string-class) value),
{[String](../dart-core/string-class) orElse()?}) →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

Returns the single element that satisfies `test`.

[skip](attributeclassset/skip)([int](../dart-core/int-class) n) →
[Iterable](../dart-core/iterable-class)\<[String](../dart-core/string-class)\>

::: {.features}
inherited
:::

Returns an [Iterable](../dart-core/iterable-class) that provides all but
the first `count` elements.

[skipWhile](attributeclassset/skipwhile)([bool](../dart-core/bool-class)
test([String](../dart-core/string-class) value)) →
[Iterable](../dart-core/iterable-class)\<[String](../dart-core/string-class)\>

::: {.features}
inherited
:::

Returns an `Iterable` that skips leading elements while `test` is
satisfied.

[take](attributeclassset/take)([int](../dart-core/int-class) n) →
[Iterable](../dart-core/iterable-class)\<[String](../dart-core/string-class)\>

::: {.features}
inherited
:::

Returns a lazy iterable of the `count` first elements of this iterable.

[takeWhile](attributeclassset/takewhile)([bool](../dart-core/bool-class)
test([String](../dart-core/string-class) value)) →
[Iterable](../dart-core/iterable-class)\<[String](../dart-core/string-class)\>

::: {.features}
inherited
:::

Returns a lazy iterable of the leading elements satisfying `test`.

[toggle](attributeclassset/toggle)([String](../dart-core/string-class)
value, \[[bool](../dart-core/bool-class)? shouldAdd\]) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Adds the class `value` to the element if it is not on it, removes it if
it is.

[toggleAll](attributeclassset/toggleall)([Iterable](../dart-core/iterable-class)\<[String](../dart-core/string-class)\>
iterable, \[[bool](../dart-core/bool-class)? shouldAdd\]) → void

::: {.features}
inherited
:::

Toggles all classes specified in `iterable` on element.

[toList](attributeclassset/tolist)({[bool](../dart-core/bool-class)
growable = true}) →
[List](../dart-core/list-class)\<[String](../dart-core/string-class)\>

::: {.features}
inherited
:::

Creates a [List](../dart-core/list-class) containing the elements of
this [Iterable](../dart-core/iterable-class).

[toSet](attributeclassset/toset)() →
[Set](../dart-core/set-class)\<[String](../dart-core/string-class)\>

::: {.features}
inherited
:::

Creates a [Set](../dart-core/set-class) with the same elements and
behavior as this `Set`.

[toString](attributeclassset/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[union](attributeclassset/union)([Set](../dart-core/set-class)\<[String](../dart-core/string-class)\>
other) →
[Set](../dart-core/set-class)\<[String](../dart-core/string-class)\>

::: {.features}
inherited
:::

Creates a new set which contains all the elements of this set and
`other`.

[where](attributeclassset/where)([bool](../dart-core/bool-class)
f([String](../dart-core/string-class) element)) →
[Iterable](../dart-core/iterable-class)\<[String](../dart-core/string-class)\>

::: {.features}
inherited
:::

Returns a new lazy [Iterable](../dart-core/iterable-class) with all
elements that satisfy the predicate `test`.

[whereType](../dart-collection/setmixin/wheretype)\<T\>() →
[Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
inherited
:::

Returns a new lazy [Iterable](../dart-core/iterable-class) with all
elements that have type `T`.

[writeClasses](attributeclassset/writeclasses)([Set](../dart-core/set-class)
s) → void

Join all the elements of a set into one string and write back to the
element. This is intended to be overridden by specific implementations.

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
<https://api.dart.dev/stable/2.18.5/dart-svg/AttributeClassSet-class.html>
:::

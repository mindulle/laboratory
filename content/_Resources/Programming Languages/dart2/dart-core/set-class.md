[dart:core](../dart-core/dart-core-library){._links-link}

Set\<E\> class
==============

A collection of objects in which each object can occur only once.

That is, for each object of the element type, the object is either
considered to be in the set, or to *not* be in the set.

Set implementations may consider some elements indistinguishable. These
elements are treated as being the same for any operation on the set.

The default [Set](set-class) implementation,
[LinkedHashSet](../dart-collection/linkedhashset-class), considers
objects indistinguishable if they are equal with regard to
[Object.==](object/operator_equals) and
[Object.hashCode](object/hashcode).

Iterating over elements of a set may be either unordered or ordered in
some way. Examples:

-   A [HashSet](../dart-collection/hashset-class) is unordered, which
    means that its iteration order is unspecified,
-   [LinkedHashSet](../dart-collection/linkedhashset-class) iterates in
    the insertion order of its elements, and
-   a sorted set like
    [SplayTreeSet](../dart-collection/splaytreeset-class) iterates the
    elements in sorted order.

It is generally not allowed to modify the set (add or remove elements)
while an operation on the set is being performed, for example during a
call to [forEach](iterable/foreach) or [containsAll](set/containsall).
Nor is it allowed to modify the set while iterating either the set
itself or any [Iterable](iterable-class) that is backed by the set, such
as the ones returned by methods like [where](iterable/where) and
[map](iterable/map).

It is generally not allowed to modify the equality of elements (and thus
not their hashcode) while they are in the set. Some specialized subtypes
may be more permissive, in which case they should document this
behavior.

Inheritance

:   -   [Object](object-class)
    -   [Iterable](iterable-class)\<E\>
    -   Set

Implementers

:   -   [CssClassSet](../dart-html/cssclassset-class)
    -   [HashSet](../dart-collection/hashset-class)
    -   [LinkedHashSet](../dart-collection/linkedhashset-class)
    -   [SetMixin](../dart-collection/setmixin-class)
    -   [UnmodifiableSetView](../dart-collection/unmodifiablesetview-class)

Available Extensions

:   -   [EnumByName](enumbyname)

Constructors
------------

[Set](set/set)()

::: {.constructor-modifier .features}
factory
:::

Creates an empty [Set](set-class).

[Set.from](set/set.from)([Iterable](iterable-class) elements)

::: {.constructor-modifier .features}
factory
:::

Creates a [Set](set-class) that contains all `elements`.

[Set.identity](set/set.identity)()

::: {.constructor-modifier .features}
factory
:::

Creates an empty identity [Set](set-class).

[Set.of](set/set.of)([Iterable](iterable-class)\<E\> elements)

::: {.constructor-modifier .features}
factory
:::

Creates a [Set](set-class) from `elements`.

[Set.unmodifiable](set/set.unmodifiable)([Iterable](iterable-class)\<E\>
elements)

::: {.constructor-modifier .features}
factory
:::

Creates an unmodifiable [Set](set-class) from `elements`.

Properties {#instance-properties}
----------

[first](iterable/first) → E

::: {.features}
read-only, inherited
:::

Returns the first element.

[hashCode](object/hashcode) → [int](int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isEmpty](iterable/isempty) → [bool](bool-class)

::: {.features}
read-only, inherited
:::

Whether this collection has no elements.

[isNotEmpty](iterable/isnotempty) → [bool](bool-class)

::: {.features}
read-only, inherited
:::

Whether this collection has at least one element.

[iterator](set/iterator) → [Iterator](iterator-class)\<E\>

::: {.features}
read-only, override
:::

An iterator that iterates over the elements of this set.

[last](iterable/last) → E

::: {.features}
read-only, inherited
:::

Returns the last element.

[length](iterable/length) → [int](int-class)

::: {.features}
read-only, inherited
:::

Returns the number of elements in [this](set-class).

[runtimeType](object/runtimetype) → [Type](type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[single](iterable/single) → E

::: {.features}
read-only, inherited
:::

Checks that this iterable has only one element, and returns that
element.

Methods {#instance-methods}
-------

[add](set/add)(E value) → [bool](bool-class)

Adds `value` to the set.

[addAll](set/addall)([Iterable](iterable-class)\<E\> elements) → void

Adds all `elements` to this set.

[any](iterable/any)([bool](bool-class) test(E element)) →
[bool](bool-class)

::: {.features}
inherited
:::

Checks whether any element of this iterable satisfies `test`.

[cast](set/cast)\<R\>() → [Set](set-class)\<R\>

::: {.features}
override
:::

Provides a view of this set as a set of `R` instances.

[clear](set/clear)() → void

Removes all elements from the set.

[contains](set/contains)([Object](object-class)? value) →
[bool](bool-class)

::: {.features}
override
:::

Whether `value` is in the set.

[containsAll](set/containsall)([Iterable](iterable-class)\<[Object](object-class)?\>
other) → [bool](bool-class)

Whether this set contains all the elements of `other`.

[difference](set/difference)([Set](set-class)\<[Object](object-class)?\>
other) → [Set](set-class)\<E\>

Creates a new set with the elements of this that are not in `other`.

[elementAt](iterable/elementat)([int](int-class) index) → E

::: {.features}
inherited
:::

Returns the `index`th element.

[every](iterable/every)([bool](bool-class) test(E element)) →
[bool](bool-class)

::: {.features}
inherited
:::

Checks whether every element of this iterable satisfies `test`.

[expand](iterable/expand)\<T\>([Iterable](iterable-class)\<T\>
toElements(E element)) → [Iterable](iterable-class)\<T\>

::: {.features}
inherited
:::

Expands each element of this [Iterable](iterable-class) into zero or
more elements.

[firstWhere](iterable/firstwhere)([bool](bool-class) test(E element), {E
orElse()?}) → E

::: {.features}
inherited
:::

Returns the first element that satisfies the given predicate `test`.

[fold](iterable/fold)\<T\>(T initialValue, T combine(T previousValue, E
element)) → T

::: {.features}
inherited
:::

Reduces a collection to a single value by iteratively combining each
element of the collection with an existing value

[followedBy](iterable/followedby)([Iterable](iterable-class)\<E\> other)
→ [Iterable](iterable-class)\<E\>

::: {.features}
inherited
:::

Returns the lazy concatenation of this iterable and `other`.

[forEach](iterable/foreach)(void action(E element)) → void

::: {.features}
inherited
:::

Invokes `action` on each element of this iterable in iteration order.

[intersection](set/intersection)([Set](set-class)\<[Object](object-class)?\>
other) → [Set](set-class)\<E\>

Creates a new set which is the intersection between this set and
`other`.

[join](iterable/join)(\[[String](string-class) separator = \"\"\]) →
[String](string-class)

::: {.features}
inherited
:::

Converts each element to a [String](string-class) and concatenates the
strings.

[lastWhere](iterable/lastwhere)([bool](bool-class) test(E element), {E
orElse()?}) → E

::: {.features}
inherited
:::

Returns the last element that satisfies the given predicate `test`.

[lookup](set/lookup)([Object](object-class)? object) → E?

If an object equal to `object` is in the set, return it.

[map](iterable/map)\<T\>(T toElement(E e)) →
[Iterable](iterable-class)\<T\>

::: {.features}
inherited
:::

The current elements of this iterable modified by `toElement`.

[noSuchMethod](object/nosuchmethod)([Invocation](invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[reduce](iterable/reduce)(E combine(E value, E element)) → E

::: {.features}
inherited
:::

Reduces a collection to a single value by iteratively combining elements
of the collection using the provided function.

[remove](set/remove)([Object](object-class)? value) → [bool](bool-class)

Removes `value` from the set.

[removeAll](set/removeall)([Iterable](iterable-class)\<[Object](object-class)?\>
elements) → void

Removes each element of `elements` from this set.

[removeWhere](set/removewhere)([bool](bool-class) test(E element)) →
void

Removes all elements of this set that satisfy `test`.

[retainAll](set/retainall)([Iterable](iterable-class)\<[Object](object-class)?\>
elements) → void

Removes all elements of this set that are not elements in `elements`.

[retainWhere](set/retainwhere)([bool](bool-class) test(E element)) →
void

Removes all elements of this set that fail to satisfy `test`.

[singleWhere](iterable/singlewhere)([bool](bool-class) test(E element),
{E orElse()?}) → E

::: {.features}
inherited
:::

Returns the single element that satisfies `test`.

[skip](iterable/skip)([int](int-class) count) →
[Iterable](iterable-class)\<E\>

::: {.features}
inherited
:::

Returns an [Iterable](iterable-class) that provides all but the first
`count` elements.

[skipWhile](iterable/skipwhile)([bool](bool-class) test(E value)) →
[Iterable](iterable-class)\<E\>

::: {.features}
inherited
:::

Returns an `Iterable` that skips leading elements while `test` is
satisfied.

[take](iterable/take)([int](int-class) count) →
[Iterable](iterable-class)\<E\>

::: {.features}
inherited
:::

Returns a lazy iterable of the `count` first elements of this iterable.

[takeWhile](iterable/takewhile)([bool](bool-class) test(E value)) →
[Iterable](iterable-class)\<E\>

::: {.features}
inherited
:::

Returns a lazy iterable of the leading elements satisfying `test`.

[toList](iterable/tolist)({[bool](bool-class) growable = true}) →
[List](list-class)\<E\>

::: {.features}
inherited
:::

Creates a [List](list-class) containing the elements of this
[Iterable](iterable-class).

[toSet](set/toset)() → [Set](set-class)\<E\>

::: {.features}
override
:::

Creates a [Set](set-class) with the same elements and behavior as this
`Set`.

[toString](iterable/tostring)() → [String](string-class)

::: {.features}
inherited
:::

Returns a string representation of (some of) the elements of `this`.

[union](set/union)([Set](set-class)\<E\> other) → [Set](set-class)\<E\>

Creates a new set which contains all the elements of this set and
`other`.

[where](iterable/where)([bool](bool-class) test(E element)) →
[Iterable](iterable-class)\<E\>

::: {.features}
inherited
:::

Returns a new lazy [Iterable](iterable-class) with all elements that
satisfy the predicate `test`.

[whereType](iterable/wheretype)\<T\>() → [Iterable](iterable-class)\<T\>

::: {.features}
inherited
:::

Returns a new lazy [Iterable](iterable-class) with all elements that
have type `T`.

Operators
---------

[operator ==](object/operator_equals)([Object](object-class) other) →
[bool](bool-class)

::: {.features}
inherited
:::

The equality operator.

Static Methods
--------------

[castFrom](set/castfrom)\<S, T\>([Set](set-class)\<S\> source,
{[Set](set-class)\<R\> newSet()?}) → [Set](set-class)\<T\>

::: {.features}
override
:::

Adapts `source` to be a `Set<T>`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Set-class.html>
:::

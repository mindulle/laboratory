[dart:collection](../dart-collection/dart-collection-library){._links-link}

SplayTreeSet\<E\> class
=======================

A [Set](../dart-core/set-class) of objects that can be ordered relative
to each other.

The set is based on a self-balancing binary tree. It allows most
operations in amortized logarithmic time.

Elements of the set are compared using the `compare` function passed in
the constructor, both for ordering and for equality. If the set contains
only an object `a`, then `set.contains(b)` will return `true` if and
only if `compare(a, b) == 0`, and the value of `a == b` is not even
checked. If the compare function is omitted, the objects are assumed to
be [Comparable](../dart-core/comparable-class), and are compared using
their [Comparable.compareTo](../dart-core/comparable/compareto) method.
Non-comparable objects (including `null`) will not work as an element in
that case.

**Note:** Do not modify a set (add or remove elements) while an
operation is being performed on that set, for example in functions
called during a [forEach](setmixin/foreach) or
[containsAll](setmixin/containsall) call, or while iterating the set.

Do not modify elements in a way which changes their equality (and thus
their hash code) while they are in the set. Some specialized kinds of
sets may be more permissive with regards to equality, in which case they
should document their different behavior and restrictions.

Example:

``` {.language-dart data-language="dart"}
final planets = SplayTreeSet<String>((a, b) => a.compareTo(b));
```

To add data to a set, use [add](splaytreeset/add) or
[addAll](splaytreeset/addall).

``` {.language-dart data-language="dart"}
planets.add('Neptune');
planets.addAll({'Venus', 'Mars', 'Earth', 'Jupiter'});
print(planets); // {Earth, Jupiter, Mars, Neptune, Venus}
```

To check if the set is empty, use [isEmpty](splaytreeset/isempty) or
[isNotEmpty](splaytreeset/isnotempty). To find the number of elements in
the set, use [length](splaytreeset/length).

``` {.language-dart data-language="dart"}
final isEmpty = planets.isEmpty; // false
final length = planets.length; // 5
```

To check whether the set contains a specific element, use
[contains](splaytreeset/contains).

``` {.language-dart data-language="dart"}
final marsExists = planets.contains('Mars'); // true
```

To get element value using index, use [elementAt](setmixin/elementat).

``` {.language-dart data-language="dart"}
final elementAt = planets.elementAt(1);
print(elementAt); // Jupiter
```

To make a copy of set, use [toSet](splaytreeset/toset).

``` {.language-dart data-language="dart"}
final copySet = planets.toSet(); // a `SplayTreeSet` with the same ordering.
print(copySet); // {Earth, Jupiter, Mars, Neptune, Venus}
```

To remove an element, use [remove](splaytreeset/remove).

``` {.language-dart data-language="dart"}
final removedValue = planets.remove('Mars'); // true
print(planets); // {Earth, Jupiter, Neptune, Venus}
```

To remove multiple elements at the same time, use
[removeWhere](setmixin/removewhere).

``` {.language-dart data-language="dart"}
planets.removeWhere((element) => element.startsWith('J'));
print(planets); // {Earth, Neptune, Venus}
```

To removes all elements in this set that do not meet a condition, use
[retainWhere](setmixin/retainwhere).

``` {.language-dart data-language="dart"}
planets.retainWhere((element) => element.contains('Earth'));
print(planets); // {Earth}
```

To remove all elements and empty the set, use
[clear](splaytreeset/clear).

``` {.language-dart data-language="dart"}
planets.clear();
print(planets.isEmpty); // true
print(planets); // {}
```

**See also:**

-   [Set](../dart-core/set-class) is a base-class for collection of
    objects.
-   [HashSet](hashset-class) the order of the objects in the iterations
    is not guaranteed.
-   [LinkedHashSet](linkedhashset-class) objects stored based on
    insertion order.

Mixed in types

:   -   [IterableMixin](iterablemixin-class)\<E\>
    -   [SetMixin](setmixin-class)\<E\>

Available Extensions

:   -   [EnumByName](../dart-core/enumbyname)

Constructors
------------

[SplayTreeSet](splaytreeset/splaytreeset)(\[[int](../dart-core/int-class)
compare(E key1, E key2)?, [bool](../dart-core/bool-class)
isValidKey(dynamic potentialKey)?\])

Create a new [SplayTreeSet](splaytreeset-class) with the given compare
function.

[SplayTreeSet.from](splaytreeset/splaytreeset.from)([Iterable](../dart-core/iterable-class)
elements, \[[int](../dart-core/int-class) compare(E key1, E key2)?,
[bool](../dart-core/bool-class) isValidKey(dynamic potentialKey)?\])

::: {.constructor-modifier .features}
factory
:::

Creates a [SplayTreeSet](splaytreeset-class) that contains all
`elements`.

[SplayTreeSet.of](splaytreeset/splaytreeset.of)([Iterable](../dart-core/iterable-class)\<E\>
elements, \[[int](../dart-core/int-class) compare(E key1, E key2)?,
[bool](../dart-core/bool-class) isValidKey(dynamic potentialKey)?\])

::: {.constructor-modifier .features}
factory
:::

Creates a [SplayTreeSet](splaytreeset-class) from `elements`.

Properties {#instance-properties}
----------

[first](splaytreeset/first) → E

::: {.features}
read-only, override
:::

Returns the first element.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isEmpty](splaytreeset/isempty) → [bool](../dart-core/bool-class)

::: {.features}
read-only, override
:::

Whether this collection has no elements.

[isNotEmpty](splaytreeset/isnotempty) → [bool](../dart-core/bool-class)

::: {.features}
read-only, override
:::

Whether this collection has at least one element.

[iterator](splaytreeset/iterator) →
[Iterator](../dart-core/iterator-class)\<E\>

::: {.features}
read-only, override
:::

Returns a new `Iterator` that allows iterating the elements of this
`Iterable`.

[last](splaytreeset/last) → E

::: {.features}
read-only, override
:::

Returns the last element.

[length](splaytreeset/length) → [int](../dart-core/int-class)

::: {.features}
read-only, override
:::

Returns the number of elements in [this](splaytreeset-class).

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[single](splaytreeset/single) → E

::: {.features}
read-only, override
:::

Checks that this iterable has only one element, and returns that
element.

Methods {#instance-methods}
-------

[add](splaytreeset/add)(E element) → [bool](../dart-core/bool-class)

::: {.features}
override
:::

Adds `value` to the set.

[addAll](splaytreeset/addall)([Iterable](../dart-core/iterable-class)\<E\>
elements) → void

::: {.features}
override
:::

Adds all `elements` to this set.

[any](setmixin/any)([bool](../dart-core/bool-class) test(E element)) →
[bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Checks whether any element of this iterable satisfies `test`.

[cast](splaytreeset/cast)\<R\>() → [Set](../dart-core/set-class)\<R\>

::: {.features}
override
:::

Provides a view of this iterable as an iterable of `R` instances.

[clear](splaytreeset/clear)() → void

::: {.features}
override
:::

Removes all elements from the set.

[contains](splaytreeset/contains)([Object](../dart-core/object-class)?
element) → [bool](../dart-core/bool-class)

::: {.features}
override
:::

Whether the collection contains an element equal to `element`.

[containsAll](setmixin/containsall)([Iterable](../dart-core/iterable-class)\<[Object](../dart-core/object-class)?\>
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Whether this set contains all the elements of `other`.

[difference](splaytreeset/difference)([Set](../dart-core/set-class)\<[Object](../dart-core/object-class)?\>
other) → [Set](../dart-core/set-class)\<E\>

::: {.features}
override
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

[intersection](splaytreeset/intersection)([Set](../dart-core/set-class)\<[Object](../dart-core/object-class)?\>
other) → [Set](../dart-core/set-class)\<E\>

::: {.features}
override
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

[lookup](splaytreeset/lookup)([Object](../dart-core/object-class)?
object) → E?

::: {.features}
override
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

[remove](splaytreeset/remove)([Object](../dart-core/object-class)?
object) → [bool](../dart-core/bool-class)

::: {.features}
override
:::

Removes `value` from the set.

[removeAll](splaytreeset/removeall)([Iterable](../dart-core/iterable-class)\<[Object](../dart-core/object-class)?\>
elements) → void

::: {.features}
override
:::

Removes each element of `elements` from this set.

[removeWhere](setmixin/removewhere)([bool](../dart-core/bool-class)
test(E element)) → void

::: {.features}
inherited
:::

Removes all elements of this set that satisfy `test`.

[retainAll](splaytreeset/retainall)([Iterable](../dart-core/iterable-class)\<[Object](../dart-core/object-class)?\>
elements) → void

::: {.features}
override
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

[toSet](splaytreeset/toset)() → [Set](../dart-core/set-class)\<E\>

::: {.features}
override
:::

Creates a [Set](../dart-core/set-class) containing the same elements as
this iterable.

[toString](splaytreeset/tostring)() →
[String](../dart-core/string-class)

::: {.features}
override
:::

A string representation of this object.

[union](splaytreeset/union)([Set](../dart-core/set-class)\<E\> other) →
[Set](../dart-core/set-class)\<E\>

::: {.features}
override
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

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SplayTreeSet-class.html>
:::

[dart:collection](../dart-collection/dart-collection-library){._links-link}

HashSet\<E\> class
==================

An unordered hash-table based [Set](../dart-core/set-class)
implementation.

The elements of a `HashSet` must have consistent equality and hashCode
implementations. This means that the equals operation must define a
stable equivalence relation on the elements (reflexive, symmetric,
transitive, and consistent over time), and that the hashCode must be
consistent with equality, so that it\'s the same for objects that are
considered equal.

Most simple operations on `HashSet` are done in (potentially amortized)
constant time: [add](../dart-core/set/add),
[contains](../dart-core/set/contains),
[remove](../dart-core/set/remove), and [length](hashset/length),
provided the hash codes of objects are well distributed.

**The iteration order of the set is not specified and depends on the
hashcodes of the provided elements.** However, the order is stable:
multiple iterations over the same set produce the same order, as long as
the set is not modified.

**Note:** Do not modify a set (add or remove elements) while an
operation is being performed on that set, for example in functions
called during a [forEach](../dart-core/iterable/foreach) or
[containsAll](../dart-core/set/containsall) call, or while iterating the
set.

Do not modify elements in a way which changes their equality (and thus
their hash code) while they are in the set. Some specialized kinds of
sets may be more permissive with regards to equality, in which case they
should document their different behavior and restrictions.

Example:

``` {.language-dart data-language="dart"}
final letters = HashSet<String>();
```

To add data to a set, use [add](../dart-core/set/add) or
[addAll](../dart-core/set/addall).

``` {.language-dart data-language="dart"}
letters.add('A');
letters.addAll({'B', 'C', 'D'});
```

To check if the set is empty, use
[isEmpty](../dart-core/iterable/isempty) or
[isNotEmpty](../dart-core/iterable/isnotempty). To find the number of
elements in the set, use [length](hashset/length).

``` {.language-dart data-language="dart"}
print(letters.isEmpty); // false
print(letters.length); // 4
print(letters); // fx {A, D, C, B}
```

To check whether the set has an element with a specific value, use
[contains](../dart-core/set/contains).

``` {.language-dart data-language="dart"}
final bExists = letters.contains('B'); // true
```

The [forEach](../dart-core/iterable/foreach) method calls a function
with each element of the set.

``` {.language-dart data-language="dart"}
letters.forEach(print);
// A
// D
// C
// B
```

To make a copy of the set, use [toSet](../dart-core/set/toset).

``` {.language-dart data-language="dart"}
final anotherSet = letters.toSet();
print(anotherSet); // fx {A, C, D, B}
```

To remove an element, use [remove](../dart-core/set/remove).

``` {.language-dart data-language="dart"}
final removedValue = letters.remove('A'); // true
print(letters); // fx {B, C, D}
```

To remove multiple elements at the same time, use
[removeWhere](../dart-core/set/removewhere) or
[removeAll](../dart-core/set/removeall).

``` {.language-dart data-language="dart"}
letters.removeWhere((element) => element.startsWith('B'));
print(letters); // fx {D, C}
```

To removes all elements in this set that do not meet a condition, use
[retainWhere](../dart-core/set/retainwhere).

``` {.language-dart data-language="dart"}
letters.retainWhere((element) => element.contains('C'));
print(letters); // {C}
```

To remove all elements and empty the set, use
[clear](../dart-core/set/clear).

``` {.language-dart data-language="dart"}
letters.clear();
print(letters.isEmpty); // true
print(letters); // {}
```

**See also:**

-   [Set](../dart-core/set-class) is the general interface of collection
    where each object can occur only once.
-   [LinkedHashSet](linkedhashset-class) objects stored based on
    insertion order.
-   [SplayTreeSet](splaytreeset-class) iterates the objects in sorted
    order.

Implemented types

:   -   [Set](../dart-core/set-class)\<E\>

Available Extensions

:   -   [EnumByName](../dart-core/enumbyname)

Constructors
------------

[HashSet](hashset/hashset)({[bool](../dart-core/bool-class) equals(E,
E)?, [int](../dart-core/int-class) hashCode(E)?,
[bool](../dart-core/bool-class) isValidKey(dynamic)?})

::: {.constructor-modifier .features}
factory
:::

Create a hash set using the provided `equals` as equality.

[HashSet.from](hashset/hashset.from)([Iterable](../dart-core/iterable-class)
elements)

::: {.constructor-modifier .features}
factory
:::

Create a hash set containing all `elements`.

[HashSet.identity](hashset/hashset.identity)()

::: {.constructor-modifier .features}
factory
:::

Creates an unordered identity-based set.

[HashSet.of](hashset/hashset.of)([Iterable](../dart-core/iterable-class)\<E\>
elements)

::: {.constructor-modifier .features}
factory
:::

Create a hash set containing all `elements`.

Properties {#instance-properties}
----------

[first](../dart-core/iterable/first) → E

::: {.features}
read-only, inherited
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

[iterator](hashset/iterator) →
[Iterator](../dart-core/iterator-class)\<E\>

::: {.features}
read-only, override
:::

Provides an iterator that iterates over the elements of this set.

[last](../dart-core/iterable/last) → E

::: {.features}
read-only, inherited
:::

Returns the last element.

[length](hashset/length) → [int](../dart-core/int-class)

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

[single](../dart-core/iterable/single) → E

::: {.features}
read-only, inherited
:::

Checks that this iterable has only one element, and returns that
element.

Methods {#instance-methods}
-------

[add](../dart-core/set/add)(E value) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Adds `value` to the set.

[addAll](../dart-core/set/addall)([Iterable](../dart-core/iterable-class)\<E\>
elements) → void

::: {.features}
inherited
:::

Adds all `elements` to this set.

[any](../dart-core/iterable/any)([bool](../dart-core/bool-class) test(E
element)) → [bool](../dart-core/bool-class)

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

[contains](../dart-core/set/contains)([Object](../dart-core/object-class)?
value) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Whether `value` is in the set.

[containsAll](../dart-core/set/containsall)([Iterable](../dart-core/iterable-class)\<[Object](../dart-core/object-class)?\>
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Whether this set contains all the elements of `other`.

[difference](../dart-core/set/difference)([Set](../dart-core/set-class)\<[Object](../dart-core/object-class)?\>
other) → [Set](../dart-core/set-class)\<E\>

::: {.features}
inherited
:::

Creates a new set with the elements of this that are not in `other`.

[elementAt](../dart-core/iterable/elementat)([int](../dart-core/int-class)
index) → E

::: {.features}
inherited
:::

Returns the `index`th element.

[every](../dart-core/iterable/every)([bool](../dart-core/bool-class)
test(E element)) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Checks whether every element of this iterable satisfies `test`.

[expand](../dart-core/iterable/expand)\<T\>([Iterable](../dart-core/iterable-class)\<T\>
toElements(E element)) → [Iterable](../dart-core/iterable-class)\<T\>

::: {.features}
inherited
:::

Expands each element of this [Iterable](../dart-core/iterable-class)
into zero or more elements.

[firstWhere](../dart-core/iterable/firstwhere)([bool](../dart-core/bool-class)
test(E element), {E orElse()?}) → E

::: {.features}
inherited
:::

Returns the first element that satisfies the given predicate `test`.

[fold](../dart-core/iterable/fold)\<T\>(T initialValue, T combine(T
previousValue, E element)) → T

::: {.features}
inherited
:::

Reduces a collection to a single value by iteratively combining each
element of the collection with an existing value

[followedBy](../dart-core/iterable/followedby)([Iterable](../dart-core/iterable-class)\<E\>
other) → [Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
inherited
:::

Returns the lazy concatenation of this iterable and `other`.

[forEach](../dart-core/iterable/foreach)(void action(E element)) → void

::: {.features}
inherited
:::

Invokes `action` on each element of this iterable in iteration order.

[intersection](../dart-core/set/intersection)([Set](../dart-core/set-class)\<[Object](../dart-core/object-class)?\>
other) → [Set](../dart-core/set-class)\<E\>

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
test(E element), {E orElse()?}) → E

::: {.features}
inherited
:::

Returns the last element that satisfies the given predicate `test`.

[lookup](../dart-core/set/lookup)([Object](../dart-core/object-class)?
object) → E?

::: {.features}
inherited
:::

If an object equal to `object` is in the set, return it.

[map](../dart-core/iterable/map)\<T\>(T toElement(E e)) →
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

[reduce](../dart-core/iterable/reduce)(E combine(E value, E element)) →
E

::: {.features}
inherited
:::

Reduces a collection to a single value by iteratively combining elements
of the collection using the provided function.

[remove](../dart-core/set/remove)([Object](../dart-core/object-class)?
value) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Removes `value` from the set.

[removeAll](../dart-core/set/removeall)([Iterable](../dart-core/iterable-class)\<[Object](../dart-core/object-class)?\>
elements) → void

::: {.features}
inherited
:::

Removes each element of `elements` from this set.

[removeWhere](../dart-core/set/removewhere)([bool](../dart-core/bool-class)
test(E element)) → void

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
test(E element)) → void

::: {.features}
inherited
:::

Removes all elements of this set that fail to satisfy `test`.

[singleWhere](../dart-core/iterable/singlewhere)([bool](../dart-core/bool-class)
test(E element), {E orElse()?}) → E

::: {.features}
inherited
:::

Returns the single element that satisfies `test`.

[skip](../dart-core/iterable/skip)([int](../dart-core/int-class) count)
→ [Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
inherited
:::

Returns an [Iterable](../dart-core/iterable-class) that provides all but
the first `count` elements.

[skipWhile](../dart-core/iterable/skipwhile)([bool](../dart-core/bool-class)
test(E value)) → [Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
inherited
:::

Returns an `Iterable` that skips leading elements while `test` is
satisfied.

[take](../dart-core/iterable/take)([int](../dart-core/int-class) count)
→ [Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
inherited
:::

Returns a lazy iterable of the `count` first elements of this iterable.

[takeWhile](../dart-core/iterable/takewhile)([bool](../dart-core/bool-class)
test(E value)) → [Iterable](../dart-core/iterable-class)\<E\>

::: {.features}
inherited
:::

Returns a lazy iterable of the leading elements satisfying `test`.

[toList](../dart-core/iterable/tolist)({[bool](../dart-core/bool-class)
growable = true}) → [List](../dart-core/list-class)\<E\>

::: {.features}
inherited
:::

Creates a [List](../dart-core/list-class) containing the elements of
this [Iterable](../dart-core/iterable-class).

[toSet](../dart-core/set/toset)() → [Set](../dart-core/set-class)\<E\>

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

[union](../dart-core/set/union)([Set](../dart-core/set-class)\<E\>
other) → [Set](../dart-core/set-class)\<E\>

::: {.features}
inherited
:::

Creates a new set which contains all the elements of this set and
`other`.

[where](../dart-core/iterable/where)([bool](../dart-core/bool-class)
test(E element)) → [Iterable](../dart-core/iterable-class)\<E\>

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
<https://api.dart.dev/stable/2.18.5/dart-collection/HashSet-class.html>
:::

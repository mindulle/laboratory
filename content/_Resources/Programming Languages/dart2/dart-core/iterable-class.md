[dart:core](../dart-core/dart-core-library){._links-link}

Iterable\<E\> class
===================

A collection of values, or \"elements\", that can be accessed
sequentially.

The elements of the iterable are accessed by getting an
[Iterator](iterator-class) using the [iterator](iterable/iterator)
getter, and using it to step through the values. Stepping with the
iterator is done by calling [Iterator.moveNext](iterator/movenext), and
if the call returns `true`, the iterator has now moved to the next
element, which is then available as
[Iterator.current](iterator/current). If the call returns `false`, there
are no more elements. The [Iterator.current](iterator/current) value
must only be used when the most recent call to
[Iterator.moveNext](iterator/movenext) has returned `true`. If it is
used before calling [Iterator.moveNext](iterator/movenext) the first
time on an iterator, or after a call has returned false or has thrown an
error, reading [Iterator.current](iterator/current) may throw or may
return an arbitrary value.

You can create more than one iterator from the same `Iterable`. Each
time `iterator` is read, it returns a new iterator, and different
iterators can be stepped through independently, each giving access to
all the elements of the iterable. The iterators of the same iterable
*should* provide the same values in the same order (unless the
underlying collection is modified between the iterations, which some
collections allow).

You can also iterate over the elements of an `Iterable` using the for-in
loop construct, which uses the `iterator` getter behind the scenes. For
example, you can iterate over all of the keys of a [Map](map-class),
because `Map` keys are iterable.

``` {.language-dart data-language="dart"}
var kidsBooks = {'Matilda': 'Roald Dahl',
                 'Green Eggs and Ham': 'Dr Seuss',
                 'Where the Wild Things Are': 'Maurice Sendak'};
for (var book in kidsBooks.keys) {
  print('$book was written by ${kidsBooks[book]}');
}
```

The [List](list-class) and [Set](set-class) classes are both `Iterable`,
as are most classes in the `dart:collection` library.

Some [Iterable](iterable-class) collections can be modified. Adding an
element to a `List` or `Set` will change which elements it contains, and
adding a new key to a `Map` changes the elements of
[Map.keys](map/keys). Iterators created after the change will provide
the new elements, and may or may not preserve the order of existing
elements (for example, a [HashSet](../dart-collection/hashset-class) may
completely change its order when a single element is added).

Changing a collection *while* it is being iterated is generally *not*
allowed. Doing so will break the iteration, which is typically signalled
by throwing a
[ConcurrentModificationError](concurrentmodificationerror-class) the
next time [Iterator.moveNext](iterator/movenext) is called. The current
value of [Iterator.current](iterator/current) getter should not be
affected by the change in the collection, the `current` value was set by
the previous call to [Iterator.moveNext](iterator/movenext).

Some iterables compute their elements dynamically every time they are
iterated, like the one returned by
[Iterable.generate](iterable/iterable.generate) or the iterable returned
by a `sync*` generator function. If the computation doesn\'t depend on
other objects that may change, then the generated sequence should be the
same one every time it\'s iterated.

The members of `Iterable`, other than `iterator` itself, work by looking
at the elements of the iterable. This can be implemented by running
through the [iterator](iterable/iterator), but some classes may have
more efficient ways of finding the result (like [last](iterable/last) or
[length](iterable/length) on a [List](list-class), or
[contains](iterable/contains) on a [Set](set-class)).

The methods that return another `Iterable` (like [map](iterable/map) and
[where](iterable/where)) are all *lazy* - they will iterate the original
(as necessary) every time the returned iterable is iterated, and not
before.

Since an iterable may be iterated more than once, it\'s not recommended
to have detectable side-effects in the iterator. For methods like
[map](iterable/map) and [where](iterable/where), the returned iterable
will execute the argument function on every iteration, so those
functions should also not have side effects.

Implementers

:   -   [DoubleLinkedQueue](../dart-collection/doublelinkedqueue-class)
    -   [IterableBase](../dart-collection/iterablebase-class)
    -   [IterableMixin](../dart-collection/iterablemixin-class)
    -   [LinkedList](../dart-collection/linkedlist-class)
    -   [List](list-class)
    -   [ListQueue](../dart-collection/listqueue-class)
    -   [Queue](../dart-collection/queue-class)
    -   [Runes](runes-class)
    -   [Set](set-class)

Available Extensions

:   -   [EnumByName](enumbyname)

Constructors
------------

[Iterable](iterable/iterable)()

::: {.constructor-modifier .features}
const
:::

[Iterable.empty](iterable/iterable.empty)()

::: {.constructor-modifier .features}
const
:::

::: {.constructor-modifier .features}
factory
:::

Creates an empty iterable.

[Iterable.generate](iterable/iterable.generate)([int](int-class) count,
\[E generator([int](int-class) index)?\])

::: {.constructor-modifier .features}
factory
:::

Creates an `Iterable` which generates its elements dynamically.

Properties {#instance-properties}
----------

[first](iterable/first) → E

::: {.features}
read-only
:::

Returns the first element.

[hashCode](object/hashcode) → [int](int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isEmpty](iterable/isempty) → [bool](bool-class)

::: {.features}
read-only
:::

Whether this collection has no elements.

[isNotEmpty](iterable/isnotempty) → [bool](bool-class)

::: {.features}
read-only
:::

Whether this collection has at least one element.

[iterator](iterable/iterator) → [Iterator](iterator-class)\<E\>

::: {.features}
read-only
:::

Returns a new `Iterator` that allows iterating the elements of this
`Iterable`.

[last](iterable/last) → E

::: {.features}
read-only
:::

Returns the last element.

[length](iterable/length) → [int](int-class)

::: {.features}
read-only
:::

Returns the number of elements in [this](iterable-class).

[runtimeType](object/runtimetype) → [Type](type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[single](iterable/single) → E

::: {.features}
read-only
:::

Checks that this iterable has only one element, and returns that
element.

Methods {#instance-methods}
-------

[any](iterable/any)([bool](bool-class) test(E element)) →
[bool](bool-class)

Checks whether any element of this iterable satisfies `test`.

[cast](iterable/cast)\<R\>() → [Iterable](iterable-class)\<R\>

Provides a view of this iterable as an iterable of `R` instances.

[contains](iterable/contains)([Object](object-class)? element) →
[bool](bool-class)

Whether the collection contains an element equal to `element`.

[elementAt](iterable/elementat)([int](int-class) index) → E

Returns the `index`th element.

[every](iterable/every)([bool](bool-class) test(E element)) →
[bool](bool-class)

Checks whether every element of this iterable satisfies `test`.

[expand](iterable/expand)\<T\>([Iterable](iterable-class)\<T\>
toElements(E element)) → [Iterable](iterable-class)\<T\>

Expands each element of this [Iterable](iterable-class) into zero or
more elements.

[firstWhere](iterable/firstwhere)([bool](bool-class) test(E element), {E
orElse()?}) → E

Returns the first element that satisfies the given predicate `test`.

[fold](iterable/fold)\<T\>(T initialValue, T combine(T previousValue, E
element)) → T

Reduces a collection to a single value by iteratively combining each
element of the collection with an existing value

[followedBy](iterable/followedby)([Iterable](iterable-class)\<E\> other)
→ [Iterable](iterable-class)\<E\>

Returns the lazy concatenation of this iterable and `other`.

[forEach](iterable/foreach)(void action(E element)) → void

Invokes `action` on each element of this iterable in iteration order.

[join](iterable/join)(\[[String](string-class) separator = \"\"\]) →
[String](string-class)

Converts each element to a [String](string-class) and concatenates the
strings.

[lastWhere](iterable/lastwhere)([bool](bool-class) test(E element), {E
orElse()?}) → E

Returns the last element that satisfies the given predicate `test`.

[map](iterable/map)\<T\>(T toElement(E e)) →
[Iterable](iterable-class)\<T\>

The current elements of this iterable modified by `toElement`.

[noSuchMethod](object/nosuchmethod)([Invocation](invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[reduce](iterable/reduce)(E combine(E value, E element)) → E

Reduces a collection to a single value by iteratively combining elements
of the collection using the provided function.

[singleWhere](iterable/singlewhere)([bool](bool-class) test(E element),
{E orElse()?}) → E

Returns the single element that satisfies `test`.

[skip](iterable/skip)([int](int-class) count) →
[Iterable](iterable-class)\<E\>

Returns an [Iterable](iterable-class) that provides all but the first
`count` elements.

[skipWhile](iterable/skipwhile)([bool](bool-class) test(E value)) →
[Iterable](iterable-class)\<E\>

Returns an `Iterable` that skips leading elements while `test` is
satisfied.

[take](iterable/take)([int](int-class) count) →
[Iterable](iterable-class)\<E\>

Returns a lazy iterable of the `count` first elements of this iterable.

[takeWhile](iterable/takewhile)([bool](bool-class) test(E value)) →
[Iterable](iterable-class)\<E\>

Returns a lazy iterable of the leading elements satisfying `test`.

[toList](iterable/tolist)({[bool](bool-class) growable = true}) →
[List](list-class)\<E\>

Creates a [List](list-class) containing the elements of this
[Iterable](iterable-class).

[toSet](iterable/toset)() → [Set](set-class)\<E\>

Creates a [Set](set-class) containing the same elements as this
iterable.

[toString](iterable/tostring)() → [String](string-class)

::: {.features}
override
:::

Returns a string representation of (some of) the elements of `this`.

[where](iterable/where)([bool](bool-class) test(E element)) →
[Iterable](iterable-class)\<E\>

Returns a new lazy [Iterable](iterable-class) with all elements that
satisfy the predicate `test`.

[whereType](iterable/wheretype)\<T\>() → [Iterable](iterable-class)\<T\>

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

[castFrom](iterable/castfrom)\<S, T\>([Iterable](iterable-class)\<S\> source) → [Iterable](iterable-class)\<T\>
:   Adapts `source` to be an `Iterable<T>`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Iterable-class.html>
:::

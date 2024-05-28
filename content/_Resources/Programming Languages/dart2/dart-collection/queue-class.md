[dart:collection](../dart-collection/dart-collection-library){._links-link}

Queue\<E\> class
================

A [Queue](queue-class) is a collection that can be manipulated at both
ends. One can iterate over the elements of a queue through
[forEach](../dart-core/iterable/foreach) or with an
[Iterator](../dart-core/iterator-class).

It is generally not allowed to modify the queue (add or remove entries)
while an operation in the queue is being performed, for example during a
call to [forEach](../dart-core/iterable/foreach). Modifying the queue
while it is being iterated will most likely break the iteration. This
goes both for using the [iterator](../dart-core/iterable/iterator)
directly, or for iterating an `Iterable` returned by a method like
[map](../dart-core/iterable/map) or
[where](../dart-core/iterable/where).

Example:

``` {.language-dart data-language="dart"}
final queue = Queue<int>(); // ListQueue() by default
print(queue.runtimeType); // ListQueue

// Adding items to queue
queue.addAll([1, 2, 3]);
queue.addFirst(0);
queue.addLast(10);
print(queue); // {0, 1, 2, 3, 10}

// Removing items from queue
queue.removeFirst();
queue.removeLast();
print(queue); // {1, 2, 3}
```

Implemented types

:   -   [Iterable](../dart-core/iterable-class)\<T\>

Implementers

:   -   [DoubleLinkedQueue](doublelinkedqueue-class)
    -   [ListQueue](listqueue-class)

Available Extensions

:   -   [EnumByName](../dart-core/enumbyname)

Constructors
------------

[Queue](queue/queue)()

::: {.constructor-modifier .features}
factory
:::

Creates a queue.

[Queue.from](queue/queue.from)([Iterable](../dart-core/iterable-class)
elements)

::: {.constructor-modifier .features}
factory
:::

Creates a queue containing all `elements`.

[Queue.of](queue/queue.of)([Iterable](../dart-core/iterable-class)\<E\>
elements)

::: {.constructor-modifier .features}
factory
:::

Creates a queue from `elements`.

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

[iterator](../dart-core/iterable/iterator) →
[Iterator](../dart-core/iterator-class)\<E\>

::: {.features}
read-only, inherited
:::

Returns a new `Iterator` that allows iterating the elements of this
`Iterable`.

[last](../dart-core/iterable/last) → E

::: {.features}
read-only, inherited
:::

Returns the last element.

[length](queue/length) → [int](../dart-core/int-class)

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

[add](queue/add)(E value) → void

Adds `value` at the end of the queue.

[addAll](queue/addall)([Iterable](../dart-core/iterable-class)\<E\>
iterable) → void

Adds all elements of `iterable` at the end of the queue. The length of
the queue is extended by the length of `iterable`.

[addFirst](queue/addfirst)(E value) → void

Adds `value` at the beginning of the queue.

[addLast](queue/addlast)(E value) → void

Adds `value` at the end of the queue.

[any](../dart-core/iterable/any)([bool](../dart-core/bool-class) test(E
element)) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Checks whether any element of this iterable satisfies `test`.

[cast](queue/cast)\<R\>() → [Queue](queue-class)\<R\>

::: {.features}
override
:::

Provides a view of this queue as a queue of `R` instances, if necessary.

[clear](queue/clear)() → void

Removes all elements in the queue. The size of the queue becomes zero.

[contains](../dart-core/iterable/contains)([Object](../dart-core/object-class)?
element) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Whether the collection contains an element equal to `element`.

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

[remove](queue/remove)([Object](../dart-core/object-class)? value) →
[bool](../dart-core/bool-class)

Removes a single instance of `value` from the queue.

[removeFirst](queue/removefirst)() → E

Removes and returns the first element of this queue.

[removeLast](queue/removelast)() → E

Removes and returns the last element of the queue.

[removeWhere](queue/removewhere)([bool](../dart-core/bool-class) test(E
element)) → void

Removes all elements matched by `test` from the queue.

[retainWhere](queue/retainwhere)([bool](../dart-core/bool-class) test(E
element)) → void

Removes all elements not matched by `test` from the queue.

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

[toSet](../dart-core/iterable/toset)() →
[Set](../dart-core/set-class)\<E\>

::: {.features}
inherited
:::

Creates a [Set](../dart-core/set-class) containing the same elements as
this iterable.

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

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

Static Methods
--------------

[castFrom](queue/castfrom)\<S, T\>([Queue](queue-class)\<S\> source) →
[Queue](queue-class)\<T\>

::: {.features}
override
:::

Adapts `source` to be a `Queue<T>`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/Queue-class.html>
:::

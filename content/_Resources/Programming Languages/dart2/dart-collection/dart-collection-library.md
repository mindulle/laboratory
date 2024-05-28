dart:collection library
=======================

Classes and utilities that supplement the collection support in
dart:core.

To use this library in your code:

``` {.language-dart data-language="dart"}
import 'dart:collection';
```

Map
---

A finite mapping from unique keys to their associated values. Allows
efficient lookup of the value associated with a key, if any, and
iterating through the individual keys and values of the map. The
[Map](../dart-core/map-class) interface has a number of implementations,
including the following:

-   [HashMap](hashmap-class) is unordered, the order of iteration is not
    guaranteed.
-   [LinkedHashMap](linkedhashmap-class) iterates in key insertion
    order.
-   [SplayTreeMap](splaytreemap-class) iterates the keys in sorted
    order.
-   [UnmodifiableMapView](unmodifiablemapview-class) is a wrapper, an
    unmodifiable [Map](../dart-core/map-class) view of another `Map`.

Set
---

A collection of objects in which each object can occur only once. The
[Set](../dart-core/set-class) interface has a number of implementations,
including the following:

-   [HashSet](hashset-class) the order of the objects in the iterations
    is not guaranteed.
-   [LinkedHashSet](linkedhashset-class) iterates the objects in
    insertion order.
-   [SplayTreeSet](splaytreeset-class) iterates the objects in sorted
    order.
-   [UnmodifiableSetView](unmodifiablesetview-class) is a wrapper, an
    unmodifiable [Set](../dart-core/set-class) view of another `Set`.

Queue
-----

A queue is a sequence of elements that is intended to be modified, by
adding or removing elements, only at its ends. Dart queues are *double
ended* queues, which means that they can be accessed equally from either
end, and can therefore be used to implement both stack and queue
behavior.

-   [Queue](queue-class) is the general interface for queues.
-   [ListQueue](listqueue-class) is a list-based queue. Default
    implementation for [Queue](queue-class).
-   [DoubleLinkedQueue](doublelinkedqueue-class) is a queue
    implementation based on a double-linked list.

List
----

An indexable Sequence of objects. Objects can be accessed using their
position, index, in the sequence. [List](../dart-core/list-class) is
also called an \"array\" in other programming languages.

-   [UnmodifiableListView](unmodifiablelistview-class) is a wrapper, an
    unmodifiable [List](../dart-core/list-class) view of another `List`.

LinkedList
----------

[LinkedList](linkedlist-class) is a specialized double-linked list of
elements that extends [LinkedListEntry](linkedlistentry-class). Each
element knows its own place in the linked list, as well as which list it
is in.

Classes
-------

[DoubleLinkedQueue](doublelinkedqueue-class)\<E\>
:   A [Queue](queue-class) implementation based on a double-linked list.

[DoubleLinkedQueueEntry](doublelinkedqueueentry-class)\<E\>
:   An entry in a doubly linked list.

[HashMap](hashmap-class)\<K, V\>
:   A hash-table based implementation of [Map](../dart-core/map-class).

[HashSet](hashset-class)\<E\>
:   An unordered hash-table based [Set](../dart-core/set-class)
    implementation.

[HasNextIterator](hasnextiterator-class)\<E\>
:   The [HasNextIterator](hasnextiterator-class) class wraps an
    [Iterator](../dart-core/iterator-class) and provides methods to
    iterate over an object using `hasNext` and `next`.

[IterableBase](iterablebase-class)\<E\>
:   Base class for implementing [Iterable](../dart-core/iterable-class).

[IterableMixin](iterablemixin-class)\<E\>
:   This [Iterable](../dart-core/iterable-class) mixin implements all
    [Iterable](../dart-core/iterable-class) members except `iterator`.

[LinkedHashMap](linkedhashmap-class)\<K, V\>
:   An insertion-ordered [Map](../dart-core/map-class) with expected
    constant-time lookup.

[LinkedHashSet](linkedhashset-class)\<E\>
:   A [LinkedHashSet](linkedhashset-class) is a hash-table based
    [Set](../dart-core/set-class) implementation.

[LinkedList](linkedlist-class)\<E extends [LinkedListEntry](linkedlistentry-class)\<E\>\>
:   A specialized double-linked list of elements that extends
    [LinkedListEntry](linkedlistentry-class).

[LinkedListEntry](linkedlistentry-class)\<E extends [LinkedListEntry](linkedlistentry-class)\<E\>\>
:   An object that can be an element in a
    [LinkedList](linkedlist-class).

[ListBase](listbase-class)\<E\>
:   Abstract implementation of a list.

[ListMixin](listmixin-class)\<E\>
:   Base implementation of a [List](../dart-core/list-class) class.

[ListQueue](listqueue-class)\<E\>
:   List based [Queue](queue-class).

[MapBase](mapbase-class)\<K, V\>
:   Base class for implementing a [Map](../dart-core/map-class).

[MapMixin](mapmixin-class)\<K, V\>
:   Mixin implementing a [Map](../dart-core/map-class).

[MapView](mapview-class)\<K, V\>
:   Wrapper around a class that implements [Map](../dart-core/map-class)
    that only exposes `Map` members.

[Queue](queue-class)\<E\>
:   A [Queue](queue-class) is a collection that can be manipulated at
    both ends. One can iterate over the elements of a queue through
    [forEach](../dart-core/iterable/foreach) or with an
    [Iterator](../dart-core/iterator-class).

[SetBase](setbase-class)\<E\>
:   Base implementation of [Set](../dart-core/set-class).

[SetMixin](setmixin-class)\<E\>
:   Mixin implementation of [Set](../dart-core/set-class).

[SplayTreeMap](splaytreemap-class)\<K, V\>
:   A [Map](../dart-core/map-class) of objects that can be ordered
    relative to each other.

[SplayTreeSet](splaytreeset-class)\<E\>
:   A [Set](../dart-core/set-class) of objects that can be ordered
    relative to each other.

[UnmodifiableListView](unmodifiablelistview-class)\<E\>
:   An unmodifiable [List](../dart-core/list-class) view of another
    List.

[UnmodifiableMapBase](unmodifiablemapbase-class)\<K, V\>
:   Basic implementation of an unmodifiable
    [Map](../dart-core/map-class).

[UnmodifiableMapView](unmodifiablemapview-class)\<K, V\>
:   View of a [Map](../dart-core/map-class) that disallow modifying the
    map.

[UnmodifiableSetView](unmodifiablesetview-class)\<E\>
:   An unmodifiable [Set](../dart-core/set-class) view of another
    [Set](../dart-core/set-class).

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/dart-collection-library.html>
:::

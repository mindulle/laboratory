[dart:core](../dart-core/dart-core-library){._links-link}

Iterator\<E\> class
===================

An interface for getting items, one at a time, from an object.

The for-in construct transparently uses `Iterator` to test for the end
of the iteration, and to get each item (or *element*).

If the object iterated over is changed during the iteration, the
behavior is unspecified.

The `Iterator` is initially positioned before the first element. Before
accessing the first element the iterator must thus be advanced using
[moveNext](iterator/movenext) to point to the first element. If no
element is left, then [moveNext](iterator/movenext) returns false, and
all further calls to [moveNext](iterator/movenext) will also return
false.

The [current](iterator/current) value must not be accessed before
calling [moveNext](iterator/movenext) or after a call to
[moveNext](iterator/movenext) has returned false.

A typical usage of an `Iterator` looks as follows:

``` {.language-dart data-language="dart"}
var it = obj.iterator;
while (it.moveNext()) {
  use(it.current);
}
```

**See also:**
[Iteration](https://dart.dev/guides/libraries/library-tour#iteration) in
the [library tour](https://dart.dev/guides/libraries/library-tour)

Implementers

:   -   [BidirectionalIterator](bidirectionaliterator-class){.deprecated}
    -   [FixedSizeListIterator](../dart-html/fixedsizelistiterator-class)

Constructors
------------

[Iterator](iterator/iterator)()

Properties {#instance-properties}
----------

[current](iterator/current) → E

::: {.features}
read-only
:::

The current element.

[hashCode](object/hashcode) → [int](int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[runtimeType](object/runtimetype) → [Type](type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[moveNext](iterator/movenext)() → [bool](bool-class)

Advances the iterator to the next element of the iteration.

[noSuchMethod](object/nosuchmethod)([Invocation](invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](object/tostring)() → [String](string-class)

::: {.features}
inherited
:::

A string representation of this object.

Operators
---------

[operator ==](object/operator_equals)([Object](object-class) other) →
[bool](bool-class)

::: {.features}
inherited
:::

The equality operator.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Iterator-class.html>
:::

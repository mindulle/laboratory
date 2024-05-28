[dart:indexed\_db](../dart-indexed_db/dart-indexed_db-library){._links-link}

Cursor class
============

Implementers

:   -   [CursorWithValue](cursorwithvalue-class)

Annotations

:   -   \@Unstable()
    -   \@Native(\"IDBCursor\")

Properties {#instance-properties}
----------

[direction](cursor/direction) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[key](cursor/key) → [Object](../dart-core/object-class)?

::: {.features}
\@\_annotation\_Creates\_IDBKey, \@\_annotation\_Returns\_IDBKey,
read-only
:::

[primaryKey](cursor/primarykey) → [Object](../dart-core/object-class)?

::: {.features}
\@\_annotation\_Creates\_IDBKey, \@\_annotation\_Returns\_IDBKey,
read-only
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[source](cursor/source) → [Object](../dart-core/object-class)?

::: {.features}
\@Creates(\'Null\'), \@Returns(\'ObjectStore\|Index\|Null\'), read-only
:::

Methods {#instance-methods}
-------

[advance](cursor/advance)([int](../dart-core/int-class) count) → void

[continuePrimaryKey](cursor/continueprimarykey)([Object](../dart-core/object-class)
key, [Object](../dart-core/object-class) primaryKey) → void

[delete](cursor/delete)() → [Future](../dart-async/future-class)

[next](cursor/next)(\[[Object](../dart-core/object-class)? key\]) → void

::: {.features}
\@JSName(\'continue\')
:::

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[update](cursor/update)(dynamic value) →
[Future](../dart-async/future-class)

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
<https://api.dart.dev/stable/2.18.5/dart-indexed_db/Cursor-class.html>
:::

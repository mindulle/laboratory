[dart:indexed\_db](../dart-indexed_db/dart-indexed_db-library){._links-link}

ObjectStore class
=================

Annotations

:   -   \@Unstable()
    -   \@Native(\"IDBObjectStore\")

Properties {#instance-properties}
----------

[autoIncrement](objectstore/autoincrement) →
[bool](../dart-core/bool-class)?

::: {.features}
read-only
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[indexNames](objectstore/indexnames) →
[List](../dart-core/list-class)\<[String](../dart-core/string-class)\>?

::: {.features}
\@Returns(\'DomStringList\'), \@Creates(\'DomStringList\'), read-only
:::

[keyPath](objectstore/keypath) → [Object](../dart-core/object-class)?

::: {.features}
\@annotation\_Creates\_SerializedScriptValue, read-only
:::

[name](objectstore/name) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[transaction](objectstore/transaction) →
[Transaction](transaction-class)?

::: {.features}
read-only
:::

Methods {#instance-methods}
-------

[add](objectstore/add)(dynamic value, \[dynamic key\]) →
[Future](../dart-async/future-class)

[clear](objectstore/clear)() → [Future](../dart-async/future-class)

[count](objectstore/count)(\[dynamic key\_OR\_range\]) →
[Future](../dart-async/future-class)\<[int](../dart-core/int-class)\>

[createIndex](objectstore/createindex)([String](../dart-core/string-class)
name, dynamic keyPath, {[bool](../dart-core/bool-class)? unique,
[bool](../dart-core/bool-class)? multiEntry}) → [Index](index-class)

[delete](objectstore/delete)(dynamic key\_OR\_keyRange) →
[Future](../dart-async/future-class)

[deleteIndex](objectstore/deleteindex)([String](../dart-core/string-class)
name) → void

[getAll](objectstore/getall)([Object](../dart-core/object-class)? query,
\[[int](../dart-core/int-class)? count\]) → [Request](request-class)

[getAllKeys](objectstore/getallkeys)([Object](../dart-core/object-class)?
query, \[[int](../dart-core/int-class)? count\]) →
[Request](request-class)

[getKey](objectstore/getkey)([Object](../dart-core/object-class) key) →
[Request](request-class)

[getObject](objectstore/getobject)(dynamic key) →
[Future](../dart-async/future-class)

[index](objectstore/index)([String](../dart-core/string-class) name) →
[Index](index-class)

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[openCursor](objectstore/opencursor)({dynamic key,
[KeyRange](keyrange-class)? range, [String](../dart-core/string-class)?
direction, [bool](../dart-core/bool-class)? autoAdvance}) →
[Stream](../dart-async/stream-class)\<[CursorWithValue](cursorwithvalue-class)\>

Creates a stream of cursors over the records in this object store.

[openKeyCursor](objectstore/openkeycursor)([Object](../dart-core/object-class)?
range, \[[String](../dart-core/string-class)? direction\]) →
[Request](request-class)

[put](objectstore/put)(dynamic value, \[dynamic key\]) →
[Future](../dart-async/future-class)

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

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
<https://api.dart.dev/stable/2.18.5/dart-indexed_db/ObjectStore-class.html>
:::

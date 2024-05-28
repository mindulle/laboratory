[dart:indexed\_db](../dart-indexed_db/dart-indexed_db-library){._links-link}

Index class
===========

Annotations

:   -   \@Unstable()
    -   \@Native(\"IDBIndex\")

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[keyPath](index/keypath) → [Object](../dart-core/object-class)?

::: {.features}
\@annotation\_Creates\_SerializedScriptValue, read-only
:::

[multiEntry](index/multientry) → [bool](../dart-core/bool-class)?

::: {.features}
read-only
:::

[name](index/name) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write
:::

[objectStore](index/objectstore) → [ObjectStore](objectstore-class)?

::: {.features}
read-only
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[unique](index/unique) → [bool](../dart-core/bool-class)?

::: {.features}
read-only
:::

Methods {#instance-methods}
-------

[count](index/count)(\[dynamic key\_OR\_range\]) →
[Future](../dart-async/future-class)\<[int](../dart-core/int-class)\>

[get](index/get)(dynamic key) → [Future](../dart-async/future-class)

[getAll](index/getall)([Object](../dart-core/object-class)? query,
\[[int](../dart-core/int-class)? count\]) → [Request](request-class)

[getAllKeys](index/getallkeys)([Object](../dart-core/object-class)?
query, \[[int](../dart-core/int-class)? count\]) →
[Request](request-class)

[getKey](index/getkey)(dynamic key) →
[Future](../dart-async/future-class)

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[openCursor](index/opencursor)({dynamic key, [KeyRange](keyrange-class)?
range, [String](../dart-core/string-class)? direction,
[bool](../dart-core/bool-class)? autoAdvance}) →
[Stream](../dart-async/stream-class)\<[CursorWithValue](cursorwithvalue-class)\>

Creates a stream of cursors over the records in this object store.

[openKeyCursor](index/openkeycursor)({dynamic key,
[KeyRange](keyrange-class)? range, [String](../dart-core/string-class)?
direction, [bool](../dart-core/bool-class)? autoAdvance}) →
[Stream](../dart-async/stream-class)\<[Cursor](cursor-class)\>

Creates a stream of cursors over the records in this object store.

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
<https://api.dart.dev/stable/2.18.5/dart-indexed_db/Index-class.html>
:::

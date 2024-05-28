[dart:indexed\_db](../dart-indexed_db/dart-indexed_db-library){._links-link}

KeyRange class
==============

Annotations

:   -   \@Unstable()
    -   \@Native(\"IDBKeyRange\")

Constructors
------------

[KeyRange.bound](keyrange/keyrange.bound)(dynamic lower, dynamic upper,
\[[bool](../dart-core/bool-class) lowerOpen = false,
[bool](../dart-core/bool-class) upperOpen = false\])

::: {.constructor-modifier .features}
factory
:::

[KeyRange.lowerBound](keyrange/keyrange.lowerbound)(dynamic bound,
\[[bool](../dart-core/bool-class) open = false\])

::: {.constructor-modifier .features}
factory
:::

[KeyRange.only](keyrange/keyrange.only)(dynamic value)

::: {.constructor-modifier .features}
factory
:::

[KeyRange.upperBound](keyrange/keyrange.upperbound)(dynamic bound,
\[[bool](../dart-core/bool-class) open = false\])

::: {.constructor-modifier .features}
factory
:::

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[lower](keyrange/lower) → [Object](../dart-core/object-class)?

::: {.features}
\@annotation\_Creates\_SerializedScriptValue, read-only
:::

[lowerOpen](keyrange/loweropen) → [bool](../dart-core/bool-class)?

::: {.features}
read-only
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[upper](keyrange/upper) → [Object](../dart-core/object-class)?

::: {.features}
\@annotation\_Creates\_SerializedScriptValue, read-only
:::

[upperOpen](keyrange/upperopen) → [bool](../dart-core/bool-class)?

::: {.features}
read-only
:::

Methods {#instance-methods}
-------

[includes](keyrange/includes)([Object](../dart-core/object-class) key) →
[bool](../dart-core/bool-class)

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

[bound\_](keyrange/bound_)([Object](../dart-core/object-class) lower,
[Object](../dart-core/object-class) upper,
\[[bool](../dart-core/bool-class)? lowerOpen,
[bool](../dart-core/bool-class)? upperOpen\]) →
[KeyRange](keyrange-class)

::: {.features}
\@JSName(\'bound\')
:::

[lowerBound\_](keyrange/lowerbound_)([Object](../dart-core/object-class)
bound, \[[bool](../dart-core/bool-class)? open\]) →
[KeyRange](keyrange-class)

::: {.features}
\@JSName(\'lowerBound\')
:::

[only\_](keyrange/only_)([Object](../dart-core/object-class) value) →
[KeyRange](keyrange-class)

::: {.features}
\@JSName(\'only\')
:::

[upperBound\_](keyrange/upperbound_)([Object](../dart-core/object-class)
bound, \[[bool](../dart-core/bool-class)? open\]) →
[KeyRange](keyrange-class)

::: {.features}
\@JSName(\'upperBound\')
:::

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-indexed_db/KeyRange-class.html>
:::

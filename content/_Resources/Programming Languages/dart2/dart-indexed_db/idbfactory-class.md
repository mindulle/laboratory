[dart:indexed\_db](../dart-indexed_db/dart-indexed_db-library){._links-link}

IdbFactory class
================

Annotations

:   -   \@SupportedBrowser(SupportedBrowser.CHROME)
    -   \@SupportedBrowser(SupportedBrowser.FIREFOX, \'15\')
    -   \@SupportedBrowser(SupportedBrowser.IE, \'10\')
    -   \@Unstable()
    -   \@Native(\"IDBFactory\")

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[supportsDatabaseNames](idbfactory/supportsdatabasenames){.deprecated} →
[bool](../dart-core/bool-class)

::: {.features}
@[Deprecated](../dart-core/deprecated-class)(\'No longer supported on
modern browsers. Always returns false.\'), read-only
:::

Deprecated. Always returns `false`.

Methods {#instance-methods}
-------

[cmp](idbfactory/cmp)([Object](../dart-core/object-class) first,
[Object](../dart-core/object-class) second) →
[int](../dart-core/int-class)

[deleteDatabase](idbfactory/deletedatabase)([String](../dart-core/string-class)
name, {void onBlocked([Event](../dart-html/event-class) e)?}) →
[Future](../dart-async/future-class)\<[IdbFactory](idbfactory-class)\>

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[open](idbfactory/open)([String](../dart-core/string-class) name,
{[int](../dart-core/int-class)? version, void
onUpgradeNeeded([VersionChangeEvent](versionchangeevent-class) event)?,
void onBlocked([Event](../dart-html/event-class) event)?}) →
[Future](../dart-async/future-class)\<[Database](database-class)\>

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

Static Properties
-----------------

[supported](idbfactory/supported) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Checks to see if Indexed DB is supported on the current platform.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-indexed_db/IdbFactory-class.html>
:::

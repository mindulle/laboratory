[dart:async](../dart-async/dart-async-library){._links-link}

DeferredLibrary class
=====================

Indicates that loading of [libraryName](deferredlibrary/libraryname) is
deferred.

This class is obsolete. Instead prefer the `deferred as` import
directive syntax.

Annotations

:   -   @[Deprecated](../dart-core/deprecated-class)(\"Dart sdk v.
        1.8\")

Constructors
------------

[DeferredLibrary](deferredlibrary/deferredlibrary)([String](../dart-core/string-class)
libraryName, {[String](../dart-core/string-class)? uri})

::: {.constructor-modifier .features}
const
:::

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[libraryName](deferredlibrary/libraryname) →
[String](../dart-core/string-class)

::: {.features}
final
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[uri](deferredlibrary/uri) → [String](../dart-core/string-class)?

::: {.features}
final
:::

Methods {#instance-methods}
-------

[load](deferredlibrary/load)() →
[Future](future-class)\<[Null](../dart-core/null-class)\>

Ensure that [libraryName](deferredlibrary/libraryname) has been loaded.

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

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/DeferredLibrary-class.html>
:::

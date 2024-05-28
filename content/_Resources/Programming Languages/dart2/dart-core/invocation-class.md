[dart:core](../dart-core/dart-core-library){._links-link}

Invocation class
================

Representation of the invocation of a member on an object.

This is the type of objects passed to
[Object.noSuchMethod](object/nosuchmethod) when an object doesn\'t
support the member invocation that was attempted on it.

Constructors
------------

[Invocation](invocation/invocation)()

[Invocation.genericMethod](invocation/invocation.genericmethod)([Symbol](symbol-class)
memberName, [Iterable](iterable-class)\<[Type](type-class)\>?
typeArguments, [Iterable](iterable-class)\<[Object](object-class)?\>?
positionalArguments, \[[Map](map-class)\<[Symbol](symbol-class),
[Object](object-class)?\>? namedArguments\])

::: {.constructor-modifier .features}
factory
:::

Creates an invocation corresponding to a generic method invocation.

[Invocation.getter](invocation/invocation.getter)([Symbol](symbol-class)
name)

::: {.constructor-modifier .features}
factory
:::

Creates an invocation corresponding to a getter invocation.

[Invocation.method](invocation/invocation.method)([Symbol](symbol-class)
memberName, [Iterable](iterable-class)\<[Object](object-class)?\>?
positionalArguments, \[[Map](map-class)\<[Symbol](symbol-class),
[Object](object-class)?\>? namedArguments\])

::: {.constructor-modifier .features}
factory
:::

Creates an invocation corresponding to a method invocation.

[Invocation.setter](invocation/invocation.setter)([Symbol](symbol-class)
memberName, [Object](object-class)? argument)

::: {.constructor-modifier .features}
factory
:::

Creates an invocation corresponding to a setter invocation.

Properties {#instance-properties}
----------

[hashCode](object/hashcode) → [int](int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isAccessor](invocation/isaccessor) → [bool](bool-class)

::: {.features}
read-only
:::

Whether the invocation was a getter or a setter call.

[isGetter](invocation/isgetter) → [bool](bool-class)

::: {.features}
read-only
:::

Whether the invocation was a getter call. If so, all three types of
arguments lists are empty.

[isMethod](invocation/ismethod) → [bool](bool-class)

::: {.features}
read-only
:::

Whether the invocation was a method call.

[isSetter](invocation/issetter) → [bool](bool-class)

::: {.features}
read-only
:::

Whether the invocation was a setter call.

[memberName](invocation/membername) → [Symbol](symbol-class)

::: {.features}
read-only
:::

The name of the invoked member.

[namedArguments](invocation/namedarguments) →
[Map](map-class)\<[Symbol](symbol-class), dynamic\>

::: {.features}
read-only
:::

An unmodifiable view of the named arguments of the call.

[positionalArguments](invocation/positionalarguments) →
[List](list-class)

::: {.features}
read-only
:::

An unmodifiable view of the positional arguments of the call.

[runtimeType](object/runtimetype) → [Type](type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[typeArguments](invocation/typearguments) →
[List](list-class)\<[Type](type-class)\>

::: {.features}
read-only
:::

An unmodifiable view of the type arguments of the call.

Methods {#instance-methods}
-------

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
<https://api.dart.dev/stable/2.18.5/dart-core/Invocation-class.html>
:::

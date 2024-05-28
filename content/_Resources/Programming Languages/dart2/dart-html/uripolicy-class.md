[dart:html](../dart-html/dart-html-library){._links-link}

UriPolicy class
===============

Defines the policy for what types of uris are allowed for particular
attribute values.

This can be used to provide custom rules such as allowing all http://
URIs for image attributes but only same-origin URIs for anchor tags.

Constructors
------------

[UriPolicy](uripolicy/uripolicy)()

::: {.constructor-modifier .features}
factory
:::

Constructs the default UriPolicy which is to only allow Uris to the same
origin as the application was launched from.

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

Methods {#instance-methods}
-------

[allowsUri](uripolicy/allowsuri)([String](../dart-core/string-class)
uri) → [bool](../dart-core/bool-class)

Checks if the uri is allowed on the specified attribute.

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
<https://api.dart.dev/stable/2.18.5/dart-html/UriPolicy-class.html>
:::

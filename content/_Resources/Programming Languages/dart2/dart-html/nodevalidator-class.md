[dart:html](../dart-html/dart-html-library){._links-link}

NodeValidator class
===================

Interface used to validate that only accepted elements and attributes
are allowed while parsing HTML strings into DOM nodes.

In general, customization of validation behavior should be done via the
[NodeValidatorBuilder](nodevalidatorbuilder-class) class to mitigate the
chances of incorrectly implementing validation rules.

Implementers

:   -   [NodeValidatorBuilder](nodevalidatorbuilder-class)

Constructors
------------

[NodeValidator](nodevalidator/nodevalidator)({[UriPolicy](uripolicy-class)?
uriPolicy})

::: {.constructor-modifier .features}
factory
:::

Construct a default NodeValidator which only accepts whitelisted HTML5
elements and attributes.

[NodeValidator.throws](nodevalidator/nodevalidator.throws)([NodeValidator](nodevalidator-class)
base)

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

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[allowsAttribute](nodevalidator/allowsattribute)([Element](element-class)
element, [String](../dart-core/string-class) attributeName,
[String](../dart-core/string-class) value) →
[bool](../dart-core/bool-class)

Returns true if the attribute is allowed.

[allowsElement](nodevalidator/allowselement)([Element](element-class)
element) → [bool](../dart-core/bool-class)

Returns true if the tagName is an accepted type.

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
<https://api.dart.dev/stable/2.18.5/dart-html/NodeValidator-class.html>
:::

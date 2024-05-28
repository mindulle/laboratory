[dart:html](../dart-html/dart-html-library){._links-link}

NodeValidatorBuilder class
==========================

Class which helps construct standard node validation policies.

By default this will not accept anything, but the \'allow\*\' functions
can be used to expand what types of elements or attributes are allowed.

All allow functions are additive- elements will be accepted if they are
accepted by any specific rule.

It is important to remember that sanitization is not just intended to
prevent cross-site scripting attacks, but also to prevent information
from being displayed in unexpected ways. For example something
displaying basic formatted text may not expect `<video>` tags to appear.
In this case an empty NodeValidatorBuilder with just
[allowTextElements](nodevalidatorbuilder/allowtextelements) might be
appropriate.

Implemented types

:   -   [NodeValidator](nodevalidator-class)

Constructors
------------

[NodeValidatorBuilder](nodevalidatorbuilder/nodevalidatorbuilder)()\
[NodeValidatorBuilder.common](nodevalidatorbuilder/nodevalidatorbuilder.common)()
:   Creates a new NodeValidatorBuilder which accepts common constructs.

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

[add](nodevalidatorbuilder/add)([NodeValidator](nodevalidator-class)
validator) → void

Add an additional validator to the current list of validators.

[allowCustomElement](nodevalidatorbuilder/allowcustomelement)([String](../dart-core/string-class)
tagName, {[UriPolicy](uripolicy-class)? uriPolicy,
[Iterable](../dart-core/iterable-class)\<[String](../dart-core/string-class)\>?
attributes,
[Iterable](../dart-core/iterable-class)\<[String](../dart-core/string-class)\>?
uriAttributes}) → void

Allow custom elements with the specified tag name and specified
attributes.

[allowElement](nodevalidatorbuilder/allowelement)([String](../dart-core/string-class)
tagName, {[UriPolicy](uripolicy-class)? uriPolicy,
[Iterable](../dart-core/iterable-class)\<[String](../dart-core/string-class)\>?
attributes,
[Iterable](../dart-core/iterable-class)\<[String](../dart-core/string-class)\>?
uriAttributes}) → void

[allowHtml5](nodevalidatorbuilder/allowhtml5)({[UriPolicy](uripolicy-class)?
uriPolicy}) → void

Allow common safe HTML5 elements and attributes.

[allowImages](nodevalidatorbuilder/allowimages)(\[[UriPolicy](uripolicy-class)?
uriPolicy\]) → void

Allows image elements.

[allowInlineStyles](nodevalidatorbuilder/allowinlinestyles)({[String](../dart-core/string-class)?
tagName}) → void

Allow inline styles on elements.

[allowNavigation](nodevalidatorbuilder/allownavigation)(\[[UriPolicy](uripolicy-class)?
uriPolicy\]) → void

Allows navigation elements- Form and Anchor tags, along with common
attributes.

[allowsAttribute](nodevalidatorbuilder/allowsattribute)([Element](element-class)
element, [String](../dart-core/string-class) attributeName,
[String](../dart-core/string-class) value) →
[bool](../dart-core/bool-class)

::: {.features}
override
:::

Returns true if the attribute is allowed.

[allowsElement](nodevalidatorbuilder/allowselement)([Element](element-class)
element) → [bool](../dart-core/bool-class)

::: {.features}
override
:::

Returns true if the tagName is an accepted type.

[allowSvg](nodevalidatorbuilder/allowsvg)() → void

Allow SVG elements and attributes except for known bad ones.

[allowTagExtension](nodevalidatorbuilder/allowtagextension)([String](../dart-core/string-class)
tagName, [String](../dart-core/string-class) baseName,
{[UriPolicy](uripolicy-class)? uriPolicy,
[Iterable](../dart-core/iterable-class)\<[String](../dart-core/string-class)\>?
attributes,
[Iterable](../dart-core/iterable-class)\<[String](../dart-core/string-class)\>?
uriAttributes}) → void

Allow custom tag extensions with the specified type name and specified
attributes.

[allowTemplating](nodevalidatorbuilder/allowtemplating)() → void

Allow templating elements (such as and template-related attributes.

[allowTextElements](nodevalidatorbuilder/allowtextelements)() → void

Allow basic text elements.

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
<https://api.dart.dev/stable/2.18.5/dart-html/NodeValidatorBuilder-class.html>
:::

[dart:html](../dart-html/dart-html-library){._links-link}

NodeTreeSanitizer class
=======================

Performs sanitization of a node tree after construction to ensure that
it does not contain any disallowed elements or attributes.

In general custom implementations of this class should not be necessary
and all validation customization should be done in custom
NodeValidators, but custom implementations of this class can be created
to perform more complex tree sanitization.

Constructors
------------

[NodeTreeSanitizer](nodetreesanitizer/nodetreesanitizer)([NodeValidator](nodevalidator-class)
validator)

::: {.constructor-modifier .features}
factory
:::

Constructs a default tree sanitizer which will remove all elements and
attributes which are not allowed by the provided validator.

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

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[sanitizeTree](nodetreesanitizer/sanitizetree)([Node](node-class) node)
→ void

Called with the root of the tree which is to be sanitized.

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

Constants
---------

[trusted](nodetreesanitizer/trusted-constant) → const \_TrustedHtmlTreeSanitizer
:   A sanitizer for trees that we trust. It does no validation and
    allows any elements. It is also more efficient, since it can pass
    the text directly through to the underlying APIs without creating a
    document fragment to be sanitized.
    <div>

    `const _TrustedHtmlTreeSanitizer()`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/NodeTreeSanitizer-class.html>
:::

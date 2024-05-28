[dart:mirrors](../dart-mirrors/dart-mirrors-library){._links-link}

Comment class
=============

Class used for encoding comments as metadata annotations.

Constructors
------------

[Comment](comment/comment)([String](../dart-core/string-class) text,
[String](../dart-core/string-class) trimmedText,
[bool](../dart-core/bool-class) isDocComment)

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

[isDocComment](comment/isdoccomment) → [bool](../dart-core/bool-class)

::: {.features}
final
:::

Is `true` if this comment is a documentation comment.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[text](comment/text) → [String](../dart-core/string-class)

::: {.features}
final
:::

The comment text as written in the source text.

[trimmedText](comment/trimmedtext) → [String](../dart-core/string-class)

::: {.features}
final
:::

The comment text without the start, end, and padding text.

Methods {#instance-methods}
-------

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
<https://api.dart.dev/stable/2.18.5/dart-mirrors/Comment-class.html>
:::

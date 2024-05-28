[dart:core](../dart-core/dart-core-library){._links-link}

Deprecated class
================

The annotation `@Deprecated('migration')` marks a feature as deprecated.

The annotation [deprecated](deprecated-constant) is a shorthand for
deprecating until an unspecified \"next release\" without migration
instructions.

A feature can be any part of an API, from a full library to a single
parameter.

The intent of the `@Deprecated` annotation is to inform authors who are
currently using the feature, that they will soon need to stop using that
feature in their code, even if the feature is currently still working
correctly.

Deprecation is an early warning that the deprecated feature is scheduled
to be removed at a later time, a time possibly specified in
[message](deprecated/message). A deprecated feature should no longer be
used, code using it will break at some point in the future. If existing
code is using the feature, that code should be rewritten to no longer
use the deprecated feature.

A deprecated feature should document how the same effect can be achieved
in [message](deprecated/message), so the programmer knows how to rewrite
the code.

The `@Deprecated` annotation applies to libraries, top-level
declarations (variables, getters, setters, functions, classes, mixins,
extension and typedefs), class-level declarations (variables, getters,
setters, methods, operators or constructors, whether static or not),
named optional parameters and trailing optional positional parameters.

Deprecation applies transitively to parts of a deprecated feature:

-   If a library is deprecated, so is every member of it.
-   If a class is deprecated, so is every member of it.
-   If a variable is deprecated, so are its implicit getter and setter.

If a feature is deprecated in a superclass, it is *not* automatically
deprecated in a subclass as well. It is reasonable to remove a member
from a superclass and retain it in a subclass, so it needs to be
possible to deprecate the member only in the superclass.

A tool that processes Dart source code may report when:

-   the code imports a deprecated library.
-   the code exports a deprecated library, or any deprecated member of a
    non-deprecated library.
-   the code refers statically to a deprecated declaration.
-   the code uses a member of an object with a statically known type,
    where the member is deprecated on the interface of the static type.
-   the code calls a method with an argument where the corresponding
    optional parameter is deprecated on the object\'s static type.

If the deprecated use is inside a library, class or method which is
itself deprecated, the tool should not bother the user about it. A
deprecated feature is expected to use other deprecated features.

Constructors
------------

[Deprecated](deprecated/deprecated)([String](string-class) message)

::: {.constructor-modifier .features}
const
:::

Create a deprecation annotation which specifies the migration path and
expiration of the annotated feature.

Properties {#instance-properties}
----------

[expires](deprecated/expires){.deprecated} → [String](string-class)

::: {.features}
@[Deprecated](deprecated-class)(\'Use \`message\` instead. Will be
removed in Dart 3.0.0\'), read-only
:::

[hashCode](object/hashcode) → [int](int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[message](deprecated/message) → [String](string-class)

::: {.features}
final
:::

Message provided to the user when they use the deprecated feature.

[runtimeType](object/runtimetype) → [Type](type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[noSuchMethod](object/nosuchmethod)([Invocation](invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](deprecated/tostring)() → [String](string-class)

::: {.features}
override
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
<https://api.dart.dev/stable/2.18.5/dart-core/Deprecated-class.html>
:::

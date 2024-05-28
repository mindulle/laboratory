[dart:developer](../dart-developer/dart-developer-library){._links-link}

UserTag class
=============

A UserTag can be used to group samples in the [DevTools CPU
profiler](https://flutter.dev/docs/development/tools/devtools/cpu-profiler).

Constructors
------------

[UserTag](usertag/usertag)([String](../dart-core/string-class) label)

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

[label](usertag/label) → [String](../dart-core/string-class)

::: {.features}
read-only
:::

Label of [this](usertag-class).

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[makeCurrent](usertag/makecurrent)() → [UserTag](usertag-class)

Make [this](usertag-class) the current tag for the isolate. Returns the
current tag before setting.

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

Static Properties
-----------------

[defaultTag](usertag/defaulttag) → [UserTag](usertag-class)

::: {.features}
read-only
:::

The default [UserTag](usertag-class) with label \'Default\'.

Constants
---------

[MAX\_USER\_TAGS](usertag/max_user_tags-constant) → const [int](../dart-core/int-class)
:   The maximum number of UserTag instances that can be created by a
    program.
    <div>

    `64`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/UserTag-class.html>
:::

[dart:core](../dart-core/dart-core-library){._links-link}

Expando\<T extends Object\> class
=================================

An [Expando](expando-class) allows adding new properties to objects.

Does not work on numbers, strings, booleans, `null`, `dart:ffi`
pointers, `dart:ffi` structs, or `dart:ffi` unions.

An `Expando` does not hold on to the added property value after an
object becomes inaccessible.

Since you can always create a new number that is identical to an
existing number, it means that an expando property on a number could
never be released. To avoid this, expando properties cannot be added to
numbers. The same argument applies to strings, booleans and `null`,
which also have literals that evaluate to identical values when they
occur more than once.

There is no restriction on other classes, even for compile time constant
objects. Be careful if adding expando properties to compile time
constants, since they will stay alive forever.

Constructors
------------

[Expando](expando/expando)(\[[String](string-class)? name\])
:   Creates a new [Expando](expando-class). The optional name is only
    used for debugging purposes and creating two different
    [Expando](expando-class)s with the same name yields two
    [Expando](expando-class)s that work on different properties of the
    objects they are used on.

Properties {#instance-properties}
----------

[hashCode](object/hashcode) → [int](int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[name](expando/name) → [String](string-class)?

::: {.features}
final
:::

The name of the this [Expando](expando-class) as passed to the
constructor.

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

[toString](expando/tostring)() → [String](string-class)

::: {.features}
override
:::

Expando toString method override.

Operators
---------

[operator ==](object/operator_equals)([Object](object-class) other) →
[bool](bool-class)

::: {.features}
inherited
:::

The equality operator.

[operator \[\]](expando/operator_get)([Object](object-class) object) →
T?

Gets the value of this [Expando](expando-class)\'s property on the given
object.

[operator \[\]=](expando/operator_put)([Object](object-class) object, T?
value) → void

Sets this [Expando](expando-class)\'s property value on the given object
to `value`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Expando-class.html>
:::

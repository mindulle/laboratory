[dart:core](../dart-core/dart-core-library){._links-link}

Null class
==========

The reserved word `null` denotes an object that is the sole instance of
this class.

The `Null` class is the only class which does not implement `Object`. It
is a compile-time error for a class to attempt to extend or implement
[Null](null-class).

The language contains a number of specialized operators for working with
`null` value. Examples:

``` {.language-dart data-language="dart"}
e1!       // Throws if e1 is null.
e2 ?? e3  // Same as e2, unless e2 is null, then use value of e3
x ??= e4  // Same as x unless x is null, then same as `x = e4`.
e5?.foo() // call `foo` on e5, unless e5 is null.
[...? e6] // spreads e6 into the list literal, unless e6 is null.
```

Properties {#instance-properties}
----------

[hashCode](null/hashcode) → [int](int-class)

::: {.features}
read-only, override
:::

The hash code for this object.

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

[toString](null/tostring)() → [String](string-class)

::: {.features}
override
:::

Returns the string `"null"`.

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
<https://api.dart.dev/stable/2.18.5/dart-core/Null-class.html>
:::

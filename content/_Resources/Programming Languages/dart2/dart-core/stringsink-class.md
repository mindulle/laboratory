[dart:core](../dart-core/dart-core-library){._links-link}

StringSink class
================

Implementers

:   -   [ClosableStringSink](../dart-convert/closablestringsink-class)
    -   [IOSink](../dart-io/iosink-class)
    -   [StringBuffer](stringbuffer-class)

Constructors
------------

[StringSink](stringsink/stringsink)()

Properties {#instance-properties}
----------

[hashCode](object/hashcode) → [int](int-class)

::: {.features}
read-only, inherited
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

[toString](object/tostring)() → [String](string-class)

::: {.features}
inherited
:::

A string representation of this object.

[write](stringsink/write)([Object](object-class)? object) → void

Writes the string representation of `object`.

[writeAll](stringsink/writeall)([Iterable](iterable-class) objects,
\[[String](string-class) separator = \"\"\]) → void

Iterates over the given `objects` and [write](stringsink/write)s them in
sequence.

[writeCharCode](stringsink/writecharcode)([int](int-class) charCode) →
void

Writes the character represented by `charCode`.

[writeln](stringsink/writeln)(\[[Object](object-class)? object = \"\"\])
→ void

Writes `object` followed by a newline, `"\n"`.

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
<https://api.dart.dev/stable/2.18.5/dart-core/StringSink-class.html>
:::

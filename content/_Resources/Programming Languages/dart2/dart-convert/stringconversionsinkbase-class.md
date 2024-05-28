[dart:convert](../dart-convert/dart-convert-library){._links-link}

StringConversionSinkBase class
==============================

This class provides a base-class for converters that need to accept
String inputs.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [StringConversionSinkMixin](stringconversionsinkmixin-class)
    -   StringConversionSinkBase

Constructors
------------

[StringConversionSinkBase](stringconversionsinkbase/stringconversionsinkbase)()

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

[add](stringconversionsinkmixin/add)([String](../dart-core/string-class)
str) → void

::: {.features}
inherited
:::

Adds chunked data to this sink.

[addSlice](stringconversionsinkmixin/addslice)([String](../dart-core/string-class)
str, [int](../dart-core/int-class) start, [int](../dart-core/int-class)
end, [bool](../dart-core/bool-class) isLast) → void

::: {.features}
inherited
:::

Adds the next `chunk` to `this`.

[asStringSink](stringconversionsinkmixin/asstringsink)() →
[ClosableStringSink](closablestringsink-class)

::: {.features}
inherited
:::

Returns `this` as a [ClosableStringSink](closablestringsink-class).

[asUtf8Sink](stringconversionsinkmixin/asutf8sink)([bool](../dart-core/bool-class)
allowMalformed) → [ByteConversionSink](byteconversionsink-class)

::: {.features}
inherited
:::

Returns `this` as a sink that accepts UTF-8 input.

[close](stringconversionsinkmixin/close)() → void

::: {.features}
inherited
:::

Closes the sink.

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
<https://api.dart.dev/stable/2.18.5/dart-convert/StringConversionSinkBase-class.html>
:::

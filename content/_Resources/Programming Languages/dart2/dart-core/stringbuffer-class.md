[dart:core](../dart-core/dart-core-library){._links-link}

StringBuffer class
==================

A class for concatenating strings efficiently.

Allows for the incremental building of a string using `write*()`
methods. The strings are concatenated to a single string only when
[toString](stringbuffer/tostring) is called.

Example:

``` {.language-dart data-language="dart"}
final buffer = StringBuffer('DART');
print(buffer.length); // 4
```

To add the string representation of an object, as returned by
[Object.toString](object/tostring), to the buffer, use
[write](stringbuffer/write). Is also used for adding a string directly.

``` {.language-dart data-language="dart"}
buffer.write(' is open source');
print(buffer.length); // 19
print(buffer); // DART is open source

const int dartYear = 2011;
buffer
  ..write(' since ') // Writes a string.
  ..write(dartYear); // Writes an int.
print(buffer); // DART is open source since 2011
print(buffer.length); // 30
```

To add a newline after the object\'s string representation, use
[writeln](stringbuffer/writeln). Calling [writeln](stringbuffer/writeln)
with no argument adds a single newline to the buffer.

``` {.language-dart data-language="dart"}
buffer.writeln(); // Contains "DART is open source since 2011\n".
buffer.writeln('-' * (buffer.length - 1)); // 30 '-'s and a newline.
print(buffer.length); // 62
```

To write multiple objects to the buffer, use
[writeAll](stringbuffer/writeall).

``` {.language-dart data-language="dart"}
const separator = '-';
buffer.writeAll(['Dart', 'is', 'fun!'], separator);
print(buffer.length); // 74
print(buffer);
// DART is open source since 2011
// ------------------------------
// Dart-is-fun!
```

To add the string representation of a Unicode code point, `charCode`, to
the buffer, use [writeCharCode](stringbuffer/writecharcode).

``` {.language-dart data-language="dart"}
buffer.writeCharCode(0x0A); // LF (line feed)
buffer.writeCharCode(0x44); // 'D'
buffer.writeCharCode(0x61); // 'a'
buffer.writeCharCode(0x72); // 'r'
buffer.writeCharCode(0x74); // 't'
print(buffer.length); // 79
```

To convert the content to a single string, use
[toString](stringbuffer/tostring).

``` {.language-dart data-language="dart"}
final text = buffer.toString();
print(text);
// DART is open source since 2011
// ------------------------------
// Dart-is-fun!
// Dart
```

To clear the buffer, so that it can be reused, use
[clear](stringbuffer/clear).

``` {.language-dart data-language="dart"}
buffer.clear();
print(buffer.isEmpty); // true
print(buffer.length); // 0
```

Implemented types

:   -   [StringSink](stringsink-class)

Constructors
------------

[StringBuffer](stringbuffer/stringbuffer)(\[[Object](object-class) content = \"\"\])
:   Creates a string buffer containing the provided `content`.

Properties {#instance-properties}
----------

[hashCode](object/hashcode) → [int](int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isEmpty](stringbuffer/isempty) → [bool](bool-class)

::: {.features}
read-only
:::

Returns whether the buffer is empty. This is a constant-time operation.

[isNotEmpty](stringbuffer/isnotempty) → [bool](bool-class)

::: {.features}
read-only
:::

Returns whether the buffer is not empty. This is a constant-time
operation.

[length](stringbuffer/length) → [int](int-class)

::: {.features}
read-only
:::

Returns the length of the content that has been accumulated so far. This
is a constant-time operation.

[runtimeType](object/runtimetype) → [Type](type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[clear](stringbuffer/clear)() → void

Clears the string buffer.

[noSuchMethod](object/nosuchmethod)([Invocation](invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](stringbuffer/tostring)() → [String](string-class)

::: {.features}
override
:::

Returns the contents of buffer as a single string.

[write](stringbuffer/write)([Object](object-class)? object) → void

::: {.features}
override
:::

Adds the string representation of `object` to the buffer.

[writeAll](stringbuffer/writeall)([Iterable](iterable-class) objects,
\[[String](string-class) separator = \"\"\]) → void

::: {.features}
override
:::

Writes all `objects` separated by `separator`.

[writeCharCode](stringbuffer/writecharcode)([int](int-class) charCode) →
void

::: {.features}
override
:::

Adds the string representation of `charCode` to the buffer.

[writeln](stringbuffer/writeln)(\[[Object](object-class)? obj = \"\"\])
→ void

::: {.features}
override
:::

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
<https://api.dart.dev/stable/2.18.5/dart-core/StringBuffer-class.html>
:::

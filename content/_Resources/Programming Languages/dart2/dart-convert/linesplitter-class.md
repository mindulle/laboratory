[dart:convert](../dart-convert/dart-convert-library){._links-link}

LineSplitter class
==================

A [StreamTransformer](../dart-async/streamtransformer-class) that splits
a [String](../dart-core/string-class) into individual lines.

A line is terminated by either:

-   a CR, carriage return: U+000D (\'\\r\')
-   a LF, line feed (Unix line break): U+000A (\'\\n\') or
-   a CR+LF sequence (DOS/Windows line break), and
-   a final non-empty line can be ended by the end of the input.

The resulting lines do not contain the line terminators.

Example:

``` {.language-dart data-language="dart"}
const splitter = LineSplitter();
const sampleText =
    'Dart is: \r an object-oriented \n class-based \n garbage-collected '
    '\r\n language with C-style syntax \r\n';

final sampleTextLines = splitter.convert(sampleText);
for (var i = 0; i < sampleTextLines.length; i++) {
  print('$i: ${sampleTextLines[i]}');
}
// 0: Dart is:
// 1:  an object-oriented
// 2:  class-based
// 3:  garbage-collected
// 4:  language with C-style syntax
```

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [StreamTransformerBase](../dart-async/streamtransformerbase-class)\<[String](../dart-core/string-class),
        [String](../dart-core/string-class)\>
    -   LineSplitter

Constructors
------------

[LineSplitter](linesplitter/linesplitter)()

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

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[bind](linesplitter/bind)([Stream](../dart-async/stream-class)\<[String](../dart-core/string-class)\>
stream) →
[Stream](../dart-async/stream-class)\<[String](../dart-core/string-class)\>

::: {.features}
override
:::

Transforms the provided `stream`.

[cast](../dart-async/streamtransformerbase/cast)\<RS, RT\>() →
[StreamTransformer](../dart-async/streamtransformer-class)\<RS, RT\>

::: {.features}
inherited
:::

Provides a `StreamTransformer<RS, RT>` view of this stream transformer.

[convert](linesplitter/convert)([String](../dart-core/string-class)
data) →
[List](../dart-core/list-class)\<[String](../dart-core/string-class)\>

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[startChunkedConversion](linesplitter/startchunkedconversion)([Sink](../dart-core/sink-class)\<[String](../dart-core/string-class)\>
sink) → [StringConversionSink](stringconversionsink-class)

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

Static Methods
--------------

[split](linesplitter/split)([String](../dart-core/string-class) lines, \[[int](../dart-core/int-class) start = 0, [int](../dart-core/int-class)? end\]) → [Iterable](../dart-core/iterable-class)\<[String](../dart-core/string-class)\>
:   Split `lines` into individual lines.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/LineSplitter-class.html>
:::

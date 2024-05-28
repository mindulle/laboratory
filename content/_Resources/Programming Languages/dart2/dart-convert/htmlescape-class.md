[dart:convert](../dart-convert/dart-convert-library){._links-link}

HtmlEscape class
================

Converter which escapes characters with special meaning in HTML.

The converter finds characters that are significant in the HTML source
and replaces them with corresponding HTML entities.

The characters that need escaping in HTML are:

-   `&` (ampersand) always needs to be escaped.
-   `<` (less than) and `>` (greater than) when inside an element.
-   `"` (quote) when inside a double-quoted attribute value.
-   `'` (apostrophe) when inside a single-quoted attribute value.
    Apostrophe is escaped as `&#39;` instead of `&apos;` since not all
    browsers understand `&apos;`.
-   `/` (slash) is recommended to be escaped because it may be used to
    terminate an element in some HTML dialects.

Escaping `>` (greater than) isn\'t necessary, but the result is often
found to be easier to read if greater-than is also escaped whenever
less-than is.

Example:

``` {.language-dart data-language="dart"}
const HtmlEscape htmlEscape = HtmlEscape();
String unescaped = 'Text & subject';
String escaped = htmlEscape.convert(unescaped);
print(escaped); // Text &amp; subject

unescaped = '10 > 1 and 1 < 10';
escaped = htmlEscape.convert(unescaped);
print(escaped); // 10 &gt; 1 and 1 &lt; 10

unescaped = "Single-quoted: 'text'";
escaped = htmlEscape.convert(unescaped);
print(escaped); // Single-quoted: &#39;text&#39;

unescaped = 'Double-quoted: "text"';
escaped = htmlEscape.convert(unescaped);
print(escaped); // Double-quoted: &quot;text&quot;

unescaped = 'Path: /system/';
escaped = htmlEscape.convert(unescaped);
print(escaped); // Path: &#47;system&#47;
```

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [StreamTransformerBase](../dart-async/streamtransformerbase-class)\<[String](../dart-core/string-class),
        [String](../dart-core/string-class)\>
    -   [Converter](converter-class)\<[String](../dart-core/string-class),
        [String](../dart-core/string-class)\>
    -   HtmlEscape

Constructors
------------

[HtmlEscape](htmlescape/htmlescape)(\[[HtmlEscapeMode](htmlescapemode-class)
mode = HtmlEscapeMode.unknown\])

::: {.constructor-modifier .features}
const
:::

Create converter that escapes HTML characters.

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[mode](htmlescape/mode) → [HtmlEscapeMode](htmlescapemode-class)

::: {.features}
final
:::

The [HtmlEscapeMode](htmlescapemode-class) used by the converter.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[bind](converter/bind)([Stream](../dart-async/stream-class)\<[String](../dart-core/string-class)\>
stream) →
[Stream](../dart-async/stream-class)\<[String](../dart-core/string-class)\>

::: {.features}
inherited
:::

Transforms the provided `stream`.

[cast](converter/cast)\<RS, RT\>() → [Converter](converter-class)\<RS,
RT\>

::: {.features}
inherited
:::

Provides a `Converter<RS, RT>` view of this stream transformer.

[convert](htmlescape/convert)([String](../dart-core/string-class) text)
→ [String](../dart-core/string-class)

::: {.features}
override
:::

Converts `input` and returns the result of the conversion.

[fuse](converter/fuse)\<TT\>([Converter](converter-class)\<[String](../dart-core/string-class),
TT\> other) →
[Converter](converter-class)\<[String](../dart-core/string-class), TT\>

::: {.features}
inherited
:::

Fuses `this` with `other`.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[startChunkedConversion](htmlescape/startchunkedconversion)([Sink](../dart-core/sink-class)\<[String](../dart-core/string-class)\>
sink) → [StringConversionSink](stringconversionsink-class)

::: {.features}
override
:::

Starts a chunked conversion.

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
<https://api.dart.dev/stable/2.18.5/dart-convert/HtmlEscape-class.html>
:::

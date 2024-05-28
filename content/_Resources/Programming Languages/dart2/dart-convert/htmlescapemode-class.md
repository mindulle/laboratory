[dart:convert](../dart-convert/dart-convert-library){._links-link}

HtmlEscapeMode class
====================

HTML escape modes.

Allows specifying a mode for HTML escaping that depends on the context
where the escaped result is going to be used. The relevant contexts are:

-   as text content of an HTML element.
-   as value of a (single- or double-) quoted attribute value.

All modes require escaping of `&` (ampersand) characters, and may enable
escaping of more characters.

Custom escape modes can be created using the
[HtmlEscapeMode.HtmlEscapeMode](htmlescapemode/htmlescapemode)
constructor.

Example:

``` {.language-dart data-language="dart"}
const htmlEscapeMode = HtmlEscapeMode(
  name: 'custom',
  escapeLtGt: true,
  escapeQuot: false,
  escapeApos: false,
  escapeSlash: false,
 );

const HtmlEscape htmlEscape = HtmlEscape(htmlEscapeMode);
String unescaped = 'Text & subject';
String escaped = htmlEscape.convert(unescaped);
print(escaped); // Text &amp; subject

unescaped = '10 > 1 and 1 < 10';
escaped = htmlEscape.convert(unescaped);
print(escaped); // 10 &gt; 1 and 1 &lt; 10

unescaped = "Single-quoted: 'text'";
escaped = htmlEscape.convert(unescaped);
print(escaped); // Single-quoted: 'text'

unescaped = 'Double-quoted: "text"';
escaped = htmlEscape.convert(unescaped);
print(escaped); // Double-quoted: "text"

unescaped = 'Path: /system/';
escaped = htmlEscape.convert(unescaped);
print(escaped); // Path: /system/
```

Constructors
------------

[HtmlEscapeMode](htmlescapemode/htmlescapemode)({[String](../dart-core/string-class)
name = \"custom\", [bool](../dart-core/bool-class) escapeLtGt = false,
[bool](../dart-core/bool-class) escapeQuot = false,
[bool](../dart-core/bool-class) escapeApos = false,
[bool](../dart-core/bool-class) escapeSlash = false})

::: {.constructor-modifier .features}
const
:::

Create a custom escaping mode.

Properties {#instance-properties}
----------

[escapeApos](htmlescapemode/escapeapos) →
[bool](../dart-core/bool-class)

::: {.features}
final
:::

Whether to escape \"\'\" (apostrophe).

[escapeLtGt](htmlescapemode/escapeltgt) →
[bool](../dart-core/bool-class)

::: {.features}
final
:::

Whether to escape \'\<\' and \'\>\'.

[escapeQuot](htmlescapemode/escapequot) →
[bool](../dart-core/bool-class)

::: {.features}
final
:::

Whether to escape \'\"\' (quote).

[escapeSlash](htmlescapemode/escapeslash) →
[bool](../dart-core/bool-class)

::: {.features}
final
:::

Whether to escape \"/\" (forward slash, solidus).

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

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](htmlescapemode/tostring)() →
[String](../dart-core/string-class)

::: {.features}
override
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

Constants
---------

[attribute](htmlescapemode/attribute-constant) → const [HtmlEscapeMode](htmlescapemode-class)
:   Escaping mode for text going into double-quoted HTML attribute
    values.
    <div>

    `HtmlEscapeMode._('attribute', true, true, false, false)`

    </div>

[element](htmlescapemode/element-constant) → const [HtmlEscapeMode](htmlescapemode-class)
:   Escaping mode for text going into HTML element content.
    <div>

    `HtmlEscapeMode._('element', true, false, false, false)`

    </div>

[sqAttribute](htmlescapemode/sqattribute-constant) → const [HtmlEscapeMode](htmlescapemode-class)
:   Escaping mode for text going into single-quoted HTML attribute
    values.
    <div>

    `HtmlEscapeMode._('attribute', true, false, true, false)`

    </div>

[unknown](htmlescapemode/unknown-constant) → const [HtmlEscapeMode](htmlescapemode-class)
:   Default escaping mode, which escapes all characters.
    <div>

    `HtmlEscapeMode._('unknown', true, true, true, true)`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/HtmlEscapeMode-class.html>
:::

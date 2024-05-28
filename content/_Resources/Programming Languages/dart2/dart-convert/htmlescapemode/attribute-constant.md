[dart:convert](../../dart-convert/dart-convert-library){._links-link}

attribute constant
==================

::: {.section .multi-line-signature}
[HtmlEscapeMode](../htmlescapemode-class) const attribute
:::

Escaping mode for text going into double-quoted HTML attribute values.

The result should not be used as the content of an unquoted or
single-quoted attribute value.

Escapes double quotes (`"`) but not single quotes (`'`), and escapes `<`
and `>` characters because they are not allowed in strict XHTML
attributes

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const HtmlEscapeMode attribute =
    HtmlEscapeMode._('attribute', true, true, false, false);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/HtmlEscapeMode/attribute-constant.html>
:::

[dart:convert](../../dart-convert/dart-convert-library){._links-link}

sqAttribute constant
====================

::: {.section .multi-line-signature}
[HtmlEscapeMode](../htmlescapemode-class) const sqAttribute
:::

Escaping mode for text going into single-quoted HTML attribute values.

The result should not be used as the content of an unquoted or
double-quoted attribute value.

Escapes single quotes (`'`) but not double quotes (`"`), and escapes `<`
and `>` characters because they are not allowed in strict XHTML
attributes.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const HtmlEscapeMode sqAttribute =
    HtmlEscapeMode._('attribute', true, false, true, false);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/HtmlEscapeMode/sqAttribute-constant.html>
:::

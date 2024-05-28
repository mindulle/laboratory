[dart:convert](../../dart-convert/dart-convert-library){._links-link}

HtmlEscape constructor
======================

::: {.section .multi-line-signature}
const HtmlEscape(

1.  \[[HtmlEscapeMode](../htmlescapemode-class) mode =
    HtmlEscapeMode.unknown\]

)
:::

Create converter that escapes HTML characters.

If [mode](mode) is provided as either
[HtmlEscapeMode.attribute](../htmlescapemode/attribute-constant) or
[HtmlEscapeMode.element](../htmlescapemode/element-constant), only the
corresponding subset of HTML characters is escaped. The default is to
escape all HTML characters.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const HtmlEscape([this.mode = HtmlEscapeMode.unknown]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/HtmlEscape/HtmlEscape.html>
:::

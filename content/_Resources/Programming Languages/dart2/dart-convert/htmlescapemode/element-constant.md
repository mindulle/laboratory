[dart:convert](../../dart-convert/dart-convert-library){._links-link}

element constant
================

::: {.section .multi-line-signature}
[HtmlEscapeMode](../htmlescapemode-class) const element
:::

Escaping mode for text going into HTML element content.

The escaping only works for elements with normal HTML content, and not,
for example, for script or style element content, which require escapes
matching their particular content syntax.

Escapes `<` and `>` characters.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const HtmlEscapeMode element =
    HtmlEscapeMode._('element', true, false, false, false);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/HtmlEscapeMode/element-constant.html>
:::

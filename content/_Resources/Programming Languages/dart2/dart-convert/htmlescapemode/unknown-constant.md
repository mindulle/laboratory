[dart:convert](../../dart-convert/dart-convert-library){._links-link}

unknown constant
================

::: {.section .multi-line-signature}
[HtmlEscapeMode](../htmlescapemode-class) const unknown
:::

Default escaping mode, which escapes all characters.

The result of such an escaping is usable both in element content and in
any attribute value.

The escaping only works for elements with normal HTML content, and not,
for example, for script or style element content, which require escapes
matching their particular content syntax.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const HtmlEscapeMode unknown =
    HtmlEscapeMode._('unknown', true, true, true, true);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/HtmlEscapeMode/unknown-constant.html>
:::

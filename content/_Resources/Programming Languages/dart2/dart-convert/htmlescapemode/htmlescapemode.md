[dart:convert](../../dart-convert/dart-convert-library){._links-link}

HtmlEscapeMode constructor
==========================

::: {.section .multi-line-signature}
const HtmlEscapeMode(

1.  {[String](../../dart-core/string-class) name = \"custom\",
2.  [bool](../../dart-core/bool-class) escapeLtGt = false,
3.  [bool](../../dart-core/bool-class) escapeQuot = false,
4.  [bool](../../dart-core/bool-class) escapeApos = false,
5.  [bool](../../dart-core/bool-class) escapeSlash = false}

)
:::

Create a custom escaping mode.

All modes escape `&`. The mode can further be set to escape `<` and `>`
([escapeLtGt](escapeltgt)), `"` ([escapeQuot](escapequot)), `'`
([escapeApos](escapeapos)), and/or `/` ([escapeSlash](escapeslash)).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const HtmlEscapeMode(
    {String name = "custom",
    this.escapeLtGt = false,
    this.escapeQuot = false,
    this.escapeApos = false,
    this.escapeSlash = false})
    : _name = name;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/HtmlEscapeMode/HtmlEscapeMode.html>
:::

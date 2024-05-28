[dart:convert](../dart-convert/dart-convert-library){._links-link}

htmlEscape top-level constant
=============================

::: {.section .multi-line-signature}
[HtmlEscape](htmlescape-class) const htmlEscape
:::

A `String` converter that converts characters to HTML entities.

This is intended to sanitize text before inserting the text into an HTML
document. Characters that are meaningful in HTML are converted to HTML
entities (like `&amp;` for `&`).

The general converter escapes all characters that are meaningful in HTML
attributes or normal element context. Elements with special content
types (like CSS or JavaScript) may need a more specialized escaping that
understands that content type.

If the context where the text will be inserted is known in more detail,
it\'s possible to omit escaping some characters (like quotes when not
inside an attribute value).

The escaped text should only be used inside quoted HTML attributes
values or as text content of a normal element. Using the escaped text
inside a tag, but not inside a quoted attribute value, is still
dangerous.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const HtmlEscape htmlEscape = HtmlEscape();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/htmlEscape-constant.html>
:::

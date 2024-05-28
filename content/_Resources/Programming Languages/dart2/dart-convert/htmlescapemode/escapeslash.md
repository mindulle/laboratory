[dart:convert](../../dart-convert/dart-convert-library){._links-link}

escapeSlash property
====================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) escapeSlash

::: {.features}
final
:::
:::

Whether to escape \"/\" (forward slash, solidus).

Escaping a slash is recommended to avoid cross-site scripting attacks by
[the Open Web Application Security
Project](https://www.owasp.org/index.php/XSS_(Cross_Site_Scripting)_Prevention_Cheat_Sheet#RULE_.231_-_HTML_Escape_Before_Inserting_Untrusted_Data_into_HTML_Element_Content)

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
final bool escapeSlash;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/HtmlEscapeMode/escapeSlash.html>
:::

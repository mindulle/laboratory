[dart:html](../../dart-html/dart-html-library){._links-link}

allowsAttribute method
======================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) allowsAttribute(

1.  [Element](../element-class) element,
2.  [String](../../dart-core/string-class) attributeName,
3.  [String](../../dart-core/string-class) value

)
:::

Returns true if the attribute is allowed.

The attributeName parameter will always be in lowercase.

See [allowsElement](allowselement) for format of tagName.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool allowsAttribute(Element element, String attributeName, String value);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/NodeValidator/allowsAttribute.html>
:::

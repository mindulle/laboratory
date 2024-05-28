[dart:html](../../dart-html/dart-html-library){._links-link}

createElementUpgrader method
============================

::: {.section .multi-line-signature}
[ElementUpgrader](../elementupgrader-class) createElementUpgrader(

1.  [Type](../../dart-core/type-class) type,
2.  {[String](../../dart-core/string-class)? extendsTag}

)
:::

Creates an element upgrader which can be used to change the Dart wrapper
type for elements.

The type specified must be a subclass of HtmlElement, when an element is
upgraded then the created constructor will be invoked on that element.

If the type is not a direct subclass of HtmlElement then the extendsTag
parameter must be provided.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ElementUpgrader createElementUpgrader(Type type, {String? extendsTag}) {
  return new _JSElementUpgrader(this, type, extendsTag);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/HtmlDocument/createElementUpgrader.html>
:::

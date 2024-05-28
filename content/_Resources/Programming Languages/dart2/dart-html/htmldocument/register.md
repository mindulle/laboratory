[dart:html](../../dart-html/dart-html-library){._links-link}

register method
===============

::: {.section .multi-line-signature}
<div>

1.  @[deprecated](../../dart-core/deprecated-constant)

</div>

void register(

1.  [String](../../dart-core/string-class) tag,
2.  [Type](../../dart-core/type-class) customElementClass,
3.  {[String](../../dart-core/string-class)? extendsTag}

)
:::

Deprecated\*: use [registerElement](../document/registerelement)
instead.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@deprecated
void register(String tag, Type customElementClass, {String? extendsTag}) {
  return registerElement(tag, customElementClass, extendsTag: extendsTag);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/HtmlDocument/register.html>
:::

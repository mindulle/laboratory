[dart:html](../../dart-html/dart-html-library){._links-link}

registerElement method
======================

::: {.section .multi-line-signature}
void registerElement(

1.  [String](../../dart-core/string-class) tag,
2.  [Type](../../dart-core/type-class) customElementClass,
3.  {[String](../../dart-core/string-class)? extendsTag}

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void registerElement(String tag, Type customElementClass,
    {String? extendsTag}) {
  registerElement2(
      tag, {'prototype': customElementClass, 'extends': extendsTag});
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Document/registerElement.html>
:::

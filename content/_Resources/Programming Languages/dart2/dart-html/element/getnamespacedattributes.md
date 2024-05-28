[dart:html](../../dart-html/dart-html-library){._links-link}

getNamespacedAttributes method
==============================

::: {.section .multi-line-signature}
[Map](../../dart-core/map-class)\<[String](../../dart-core/string-class),
[String](../../dart-core/string-class)\> getNamespacedAttributes(

1.  [String](../../dart-core/string-class) namespace

)
:::

Gets a map for manipulating the attributes of a particular namespace.

This is primarily useful for SVG attributes such as xref:link.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Map<String, String> getNamespacedAttributes(String namespace) {
  return new _NamespacedAttributeMap(this, namespace);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/getNamespacedAttributes.html>
:::

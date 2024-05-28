[dart:html](../../dart-html/dart-html-library){._links-link}

attributes property
===================

::: {#getter .section .multi-line-signature}
[Map](../../dart-core/map-class)\<[String](../../dart-core/string-class),
[String](../../dart-core/string-class)\> attributes
:::

All attributes on this element.

Any modifications to the attribute map will automatically be applied to
this element.

This only includes attributes which are not in a namespace (such as
\'xlink:href\'), additional attributes can be accessed via
[getNamespacedAttributes](getnamespacedattributes).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Map<String, String> get attributes => new _ElementAttributeMap(this);
```

::: {#setter .section .multi-line-signature}
void
attributes=([Map](../../dart-core/map-class)\<[String](../../dart-core/string-class),
[String](../../dart-core/string-class)\> value)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set attributes(Map<String, String> value) {
  Map<String, String> attributes = this.attributes;
  attributes.clear();
  for (String key in value.keys) {
    attributes[key] = value[key]!;
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/attributes.html>
:::

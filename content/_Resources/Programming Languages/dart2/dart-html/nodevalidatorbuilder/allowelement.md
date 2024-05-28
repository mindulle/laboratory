[dart:html](../../dart-html/dart-html-library){._links-link}

allowElement method
===================

::: {.section .multi-line-signature}
void allowElement(

1.  [String](../../dart-core/string-class) tagName,
2.  {[UriPolicy](../uripolicy-class)? uriPolicy,
3.  [Iterable](../../dart-core/iterable-class)\<[String](../../dart-core/string-class)\>?
    attributes,
4.  [Iterable](../../dart-core/iterable-class)\<[String](../../dart-core/string-class)\>?
    uriAttributes}

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void allowElement(String tagName,
    {UriPolicy? uriPolicy,
    Iterable<String>? attributes,
    Iterable<String>? uriAttributes}) {
  allowCustomElement(tagName,
      uriPolicy: uriPolicy,
      attributes: attributes,
      uriAttributes: uriAttributes);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/NodeValidatorBuilder/allowElement.html>
:::

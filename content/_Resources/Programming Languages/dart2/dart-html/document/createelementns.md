[dart:html](../../dart-html/dart-html-library){._links-link}

createElementNS method
======================

::: {.section .multi-line-signature}
[Element](../element-class) createElementNS(

1.  [String](../../dart-core/string-class) namespaceURI,
2.  [String](../../dart-core/string-class) qualifiedName,
3.  \[[String](../../dart-core/string-class)? typeExtension\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Element createElementNS(String namespaceURI, String qualifiedName,
    [String? typeExtension]) {
  return (typeExtension == null)
      ? _createElementNS_2(namespaceURI, qualifiedName)
      : _createElementNS(namespaceURI, qualifiedName, typeExtension);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Document/createElementNS.html>
:::

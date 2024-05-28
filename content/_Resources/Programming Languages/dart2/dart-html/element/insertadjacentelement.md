[dart:html](../../dart-html/dart-html-library){._links-link}

insertAdjacentElement method
============================

::: {.section .multi-line-signature}
[Element](../element-class) insertAdjacentElement(

1.  [String](../../dart-core/string-class) where,
2.  [Element](../element-class) element

)
:::

Inserts `element` into the DOM at the specified location.

To see the possible values for `where`, read the doc for
[insertAdjacentHtml](insertadjacenthtml).

See also:

-   [insertAdjacentHtml](insertadjacenthtml)

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Element insertAdjacentElement(String where, Element element) {
  if (JS('bool', '!!#.insertAdjacentElement', this)) {
    _insertAdjacentElement(where, element);
  } else {
    _insertAdjacentNode(where, element);
  }
  return element;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/insertAdjacentElement.html>
:::

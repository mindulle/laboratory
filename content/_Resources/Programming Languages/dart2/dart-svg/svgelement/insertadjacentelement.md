[dart:svg](../../dart-svg/dart-svg-library){._links-link}

insertAdjacentElement method
============================

::: {.section .multi-line-signature}
[Element](../../dart-html/element-class) insertAdjacentElement(

1.  [String](../../dart-core/string-class) where,
2.  [Element](../../dart-html/element-class) element

)

::: {.features}
override
:::
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
  throw new UnsupportedError("Cannot invoke insertAdjacentElement on SVG.");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/SvgElement/insertAdjacentElement.html>
:::

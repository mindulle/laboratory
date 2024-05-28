[dart:svg](../../dart-svg/dart-svg-library){._links-link}

insertAdjacentText method
=========================

::: {.section .multi-line-signature}
void insertAdjacentText(

1.  [String](../../dart-core/string-class) where,
2.  [String](../../dart-core/string-class) text

)

::: {.features}
override
:::
:::

Inserts text into the DOM at the specified location.

To see the possible values for `where`, read the doc for
[insertAdjacentHtml](insertadjacenthtml).

See also:

-   [insertAdjacentHtml](insertadjacenthtml)

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void insertAdjacentText(String where, String text) {
  throw new UnsupportedError("Cannot invoke insertAdjacentText on SVG.");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/SvgElement/insertAdjacentText.html>
:::

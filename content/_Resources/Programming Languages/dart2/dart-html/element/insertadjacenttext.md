[dart:html](../../dart-html/dart-html-library){._links-link}

insertAdjacentText method
=========================

::: {.section .multi-line-signature}
void insertAdjacentText(

1.  [String](../../dart-core/string-class) where,
2.  [String](../../dart-core/string-class) text

)
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
  if (JS('bool', '!!#.insertAdjacentText', this)) {
    _insertAdjacentText(where, text);
  } else {
    _insertAdjacentNode(where, new Text(text));
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/insertAdjacentText.html>
:::

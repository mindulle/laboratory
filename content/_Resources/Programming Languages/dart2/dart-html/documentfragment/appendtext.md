[dart:html](../../dart-html/dart-html-library){._links-link}

appendText method
=================

::: {.section .multi-line-signature}
void appendText(

1.  [String](../../dart-core/string-class) text

)
:::

Adds the specified text as a text node after the last child of this
document fragment.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void appendText(String text) {
  this.append(new Text(text));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/DocumentFragment/appendText.html>
:::

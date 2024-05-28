[dart:html](../../dart-html/dart-html-library){._links-link}

allowTextElements method
========================

::: {.section .multi-line-signature}
void allowTextElements()
:::

Allow basic text elements.

This allows a subset of HTML5 elements, specifically just these tags and
no attributes.

-   B
-   BLOCKQUOTE
-   BR
-   EM
-   H1
-   H2
-   H3
-   H4
-   H5
-   H6
-   HR
-   I
-   LI
-   OL
-   P
-   SPAN
-   UL

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void allowTextElements() {
  add(new _SimpleNodeValidator.allowTextElements());
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/NodeValidatorBuilder/allowTextElements.html>
:::

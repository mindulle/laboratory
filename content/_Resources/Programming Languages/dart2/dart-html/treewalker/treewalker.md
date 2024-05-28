[dart:html](../../dart-html/dart-html-library){._links-link}

TreeWalker constructor
======================

::: {.section .multi-line-signature}
TreeWalker(

1.  [Node](../node-class) root,
2.  [int](../../dart-core/int-class) whatToShow

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory TreeWalker(Node root, int whatToShow) {
  return document._createTreeWalker(root, whatToShow, null);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/TreeWalker/TreeWalker.html>
:::

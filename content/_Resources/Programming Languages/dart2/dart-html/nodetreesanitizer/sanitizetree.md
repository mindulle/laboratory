[dart:html](../../dart-html/dart-html-library){._links-link}

sanitizeTree method
===================

::: {.section .multi-line-signature}
void sanitizeTree(

1.  [Node](../node-class) node

)
:::

Called with the root of the tree which is to be sanitized.

This method needs to walk the entire tree and either remove elements and
attributes which are not recognized as safe or throw an exception which
will mark the entire tree as unsafe.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void sanitizeTree(Node node);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/NodeTreeSanitizer/sanitizeTree.html>
:::

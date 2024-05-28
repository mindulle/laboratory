[dart:html](../../dart-html/dart-html-library){._links-link}

replaceWith method
==================

::: {.section .multi-line-signature}
[Node](../node-class) replaceWith(

1.  [Node](../node-class) otherNode

)
:::

Replaces this node with another node.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Node replaceWith(Node otherNode) {
  try {
    final Node parent = this.parentNode!;
    parent._replaceChild(otherNode, this);
  } catch (e) {}
  return this;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Node/replaceWith.html>
:::

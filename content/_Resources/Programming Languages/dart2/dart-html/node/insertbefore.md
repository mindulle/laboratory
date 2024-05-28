[dart:html](../../dart-html/dart-html-library){._links-link}

insertBefore method
===================

::: {.section .multi-line-signature}
[Node](../node-class) insertBefore(

1.  [Node](../node-class) node,
2.  [Node](../node-class)? child

)
:::

Inserts the given node into this node directly before child. If child is
`null`, then the given node is inserted at the end of this node\'s child
nodes.

Other resources
---------------

-   [Node.insertBefore](https://developer.mozilla.org/en-US/docs/Web/API/Node.insertBefore)
    from MDN.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Node insertBefore(Node node, Node? child) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Node/insertBefore.html>
:::

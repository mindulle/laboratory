[dart:html](../../dart-html/dart-html-library){._links-link}

insertAllBefore method
======================

::: {.section .multi-line-signature}
void insertAllBefore(

1.  [Iterable](../../dart-core/iterable-class)\<[Node](../node-class)\>
    newNodes,
2.  [Node](../node-class) child

)
:::

Inserts all of the nodes into this node directly before child.

See also:

-   [insertBefore](insertbefore)

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void insertAllBefore(Iterable<Node> newNodes, Node child) {
  if (newNodes is _ChildNodeListLazy) {
    _ChildNodeListLazy otherList = newNodes;
    if (identical(otherList._this, this)) {
      throw new ArgumentError(newNodes);
    }

    // Optimized route for copying between nodes.
    for (var i = 0, len = otherList.length; i < len; ++i) {
      this.insertBefore(otherList._this.firstChild!, child);
    }
  } else {
    for (var node in newNodes) {
      this.insertBefore(node, child);
    }
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Node/insertAllBefore.html>
:::

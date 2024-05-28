[dart:html](../../dart-html/dart-html-library){._links-link}

nodes property
==============

::: {#getter .section .multi-line-signature}
[List](../../dart-core/list-class)\<[Node](../node-class)\> nodes
:::

A modifiable list of this node\'s children.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
List<Node> get nodes {
  return new _ChildNodeListLazy(this);
}
```

::: {#setter .section .multi-line-signature}
void
nodes=([Iterable](../../dart-core/iterable-class)\<[Node](../node-class)\>
value)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set nodes(Iterable<Node> value) {
  // Copy list first since we don't want liveness during iteration.
  // TODO(jacobr): there is a better way to do this.
  var copy = value.toList();
  text = '';
  for (Node node in copy) {
    append(node);
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Node/nodes.html>
:::

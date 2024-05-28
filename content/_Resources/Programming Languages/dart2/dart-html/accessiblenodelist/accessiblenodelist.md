[dart:html](../../dart-html/dart-html-library){._links-link}

AccessibleNodeList constructor
==============================

::: {.section .multi-line-signature}
AccessibleNodeList(

1.  \[[List](../../dart-core/list-class)\<[AccessibleNode](../accessiblenode-class)\>?
    nodes\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory AccessibleNodeList([List<AccessibleNode>? nodes]) {
  if (nodes != null) {
    return AccessibleNodeList._create_1(nodes);
  }
  return AccessibleNodeList._create_2();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/AccessibleNodeList/AccessibleNodeList.html>
:::

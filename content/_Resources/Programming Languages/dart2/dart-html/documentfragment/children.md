[dart:html](../../dart-html/dart-html-library){._links-link}

children property
=================

::: {#getter .section .multi-line-signature}
[List](../../dart-core/list-class)\<[Element](../element-class)\>
children
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
List<Element> get children {
  if (_docChildren == null) {
    _docChildren = new FilteredElementList(this);
  }
  return _docChildren!;
}
```

::: {#setter .section .multi-line-signature}
void
children=([List](../../dart-core/list-class)\<[Element](../element-class)\>
value)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set children(List<Element> value) {
  // Copy list first since we don't want liveness during iteration.
  var copy = value.toList();
  var children = this.children;
  children.clear();
  children.addAll(copy);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/DocumentFragment/children.html>
:::

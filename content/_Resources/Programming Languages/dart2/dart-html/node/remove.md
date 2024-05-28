[dart:html](../../dart-html/dart-html-library){._links-link}

remove method
=============

::: {.section .multi-line-signature}
void remove()
:::

Removes this node from the DOM.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void remove() {
  // TODO(jacobr): should we throw an exception if parent is already null?
  // TODO(vsm): Use the native remove when available.
  if (this.parentNode != null) {
    final Node parent = this.parentNode!;
    parent._removeChild(this);
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Node/remove.html>
:::

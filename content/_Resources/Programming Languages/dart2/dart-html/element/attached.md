[dart:html](../../dart-html/dart-html-library){._links-link}

attached method
===============

::: {.section .multi-line-signature}
void attached()
:::

Called by the DOM when this element has been inserted into the live
document.

More information can be found in the [Custom
Elements](http://w3c.github.io/webcomponents/spec/custom/#dfn-attached-callback)
draft specification.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void attached() {
  // For the deprecation period, call the old callback.
  enteredView();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/attached.html>
:::

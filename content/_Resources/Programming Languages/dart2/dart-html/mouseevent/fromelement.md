[dart:html](../../dart-html/dart-html-library){._links-link}

fromElement property
====================

::: {#getter .section .multi-line-signature}
[Node](../node-class)? fromElement
:::

The nonstandard way to access the element that the mouse comes from in
the case of a `mouseover` event.

This member is deprecated and not cross-browser compatible; use
relatedTarget to get the same information in the standard way.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@deprecated
Node? get fromElement native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MouseEvent/fromElement.html>
:::

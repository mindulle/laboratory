[dart:html](../../dart-html/dart-html-library){._links-link}

toElement property
==================

::: {#getter .section .multi-line-signature}
[Node](../node-class)? toElement
:::

The nonstandard way to access the element that the mouse goes to in the
case of a `mouseout` event.

This member is deprecated and not cross-browser compatible; use
relatedTarget to get the same information in the standard way.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@deprecated
Node? get toElement native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MouseEvent/toElement.html>
:::

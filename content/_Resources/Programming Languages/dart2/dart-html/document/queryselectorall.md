[dart:html](../../dart-html/dart-html-library){._links-link}

querySelectorAll\<T extends Element\> method
============================================

::: {.section .multi-line-signature}
[ElementList](../elementlist-class)\<T\> querySelectorAll\<T extends
Element\>(

1.  [String](../../dart-core/string-class) selectors

)
:::

Finds all descendant elements of this document that match the specified
group of selectors.

Unless your webpage contains multiple documents, the top-level
[querySelectorAll](queryselectorall) method behaves the same as this
method, so you should use it instead to save typing a few characters.

`selectors` should be a string using CSS selector syntax.

``` {.language-dart data-language="dart"}
var items = document.querySelectorAll('.itemClassName');
```

For details about CSS selector syntax, see the [CSS selector
specification](http://www.w3.org/TR/css3-selectors/).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ElementList<T> querySelectorAll<T extends Element>(String selectors) =>
    new _FrozenElementList<T>._wrap(_querySelectorAll(selectors));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Document/querySelectorAll.html>
:::

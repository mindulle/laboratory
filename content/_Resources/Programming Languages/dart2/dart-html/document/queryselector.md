[dart:html](../../dart-html/dart-html-library){._links-link}

querySelector method
====================

::: {.section .multi-line-signature}
[Element](../element-class)? querySelector(

1.  [String](../../dart-core/string-class) selectors

)
:::

Finds the first descendant element of this document that matches the
specified group of selectors.

Unless your webpage contains multiple documents, the top-level
[querySelector](queryselector) method behaves the same as this method,
so you should use it instead to save typing a few characters.

`selectors` should be a string using CSS selector syntax.

``` {.language-dart data-language="dart"}
var element1 = document.querySelector('.className');
var element2 = document.querySelector('#id');
```

For details about CSS selector syntax, see the [CSS selector
specification](http://www.w3.org/TR/css3-selectors/).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Element? querySelector(String selectors) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Document/querySelector.html>
:::

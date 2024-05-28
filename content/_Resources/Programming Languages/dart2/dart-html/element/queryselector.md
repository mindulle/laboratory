[dart:html](../../dart-html/dart-html-library){._links-link}

querySelector method
====================

::: {.section .multi-line-signature}
[Element](../element-class)? querySelector(

1.  [String](../../dart-core/string-class) selectors

)

::: {.features}
override
:::
:::

Finds the first descendant element of this element that matches the
specified group of selectors.

`selectors` should be a string using CSS selector syntax.

``` {.language-dart data-language="dart"}
// Gets the first descendant with the class 'classname'
var element = element.querySelector('.className');
// Gets the element with id 'id'
var element = element.querySelector('#id');
// Gets the first descendant [ImageElement]
var img = element.querySelector('img');
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
<https://api.dart.dev/stable/2.18.5/dart-html/Element/querySelector.html>
:::

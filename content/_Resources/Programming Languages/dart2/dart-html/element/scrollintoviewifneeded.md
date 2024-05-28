[dart:html](../../dart-html/dart-html-library){._links-link}

scrollIntoViewIfNeeded method
=============================

::: {.section .multi-line-signature}
void scrollIntoViewIfNeeded(

1.  \[[bool](../../dart-core/bool-class)? centerIfNeeded\]

)
:::

Nonstandard version of `scrollIntoView` that scrolls the current element
into the visible area of the browser window if it\'s not already within
the visible area of the browser window. If the element is already within
the visible area of the browser window, then no scrolling takes place.

Other resources
---------------

-   [Element.scrollIntoViewIfNeeded](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollIntoViewIfNeeded)
    from MDN.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void scrollIntoViewIfNeeded([bool? centerIfNeeded]) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/scrollIntoViewIfNeeded.html>
:::

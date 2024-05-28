[dart:html](../../dart-html/dart-html-library){._links-link}

getBoundingClientRect method
============================

::: {.section .multi-line-signature}
<div>

1.  \@Creates(\'\_DomRect\')
2.  \@Returns(\'\_DomRect\|Null\')

</div>

[Rectangle](../../dart-math/rectangle-class)\<[num](../../dart-core/num-class)\>
getBoundingClientRect()

::: {.features}
\@Creates(\'\_DomRect\'), \@Returns(\'\_DomRect\|Null\')
:::
:::

Returns the smallest bounding rectangle that encompasses this element\'s
padding, scrollbar, and border.

Other resources
---------------

-   [Element.getBoundingClientRect](https://developer.mozilla.org/en-US/docs/Web/API/Element.getBoundingClientRect)
    from MDN.
-   [The getBoundingClientRect()
    method](http://www.w3.org/TR/cssom-view/#the-getclientrects()-and-getboundingclientrect()-methods)
    from W3C.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Creates('_DomRect')
@Returns('_DomRect|Null')
Rectangle getBoundingClientRect() native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/getBoundingClientRect.html>
:::

[dart:html](../../dart-html/dart-html-library){._links-link}

getElementsByClassName method
=============================

::: {.section .multi-line-signature}
<div>

1.  \@Creates(\'NodeList\|HtmlCollection\')
2.  \@Returns(\'NodeList\|HtmlCollection\')

</div>

[List](../../dart-core/list-class)\<[Node](../node-class)\>
getElementsByClassName(

1.  [String](../../dart-core/string-class) classNames

)

::: {.features}
\@Creates(\'NodeList\|HtmlCollection\'),
\@Returns(\'NodeList\|HtmlCollection\')
:::
:::

Returns a list of nodes with the given class name inside this element.

Other resources
---------------

-   [getElementsByClassName](https://developer.mozilla.org/en-US/docs/Web/API/document.getElementsByClassName)
    from MDN.
-   [DOM specification](http://www.w3.org/TR/domcore/) from W3C.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Creates('NodeList|HtmlCollection')
@Returns('NodeList|HtmlCollection')
List<Node> getElementsByClassName(String classNames) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/getElementsByClassName.html>
:::

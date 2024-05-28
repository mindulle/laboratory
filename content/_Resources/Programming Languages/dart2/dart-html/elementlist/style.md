[dart:html](../../dart-html/dart-html-library){._links-link}

style property
==============

::: {#getter .section .multi-line-signature}
[CssStyleDeclarationBase](../cssstyledeclarationbase-class) style
:::

Access the union of all
[CssStyleDeclaration](../cssstyledeclaration-class)s that are associated
with an [ElementList](../elementlist-class).

Grouping the style objects all together provides easy editing of
specific properties of a collection of elements. Setting a specific
property value will set that property in all
[Element](../element-class)s in the [ElementList](../elementlist-class).
Getting a specific property value will return the value of the property
of the first element in the [ElementList](../elementlist-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
CssStyleDeclarationBase get style;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/ElementList/style.html>
:::

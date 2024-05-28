[dart:html](../../dart-html/dart-html-library){._links-link}

getElementsByName method
========================

::: {.section .multi-line-signature}
<div>

1.  \@Creates(\'NodeList\|HtmlCollection\')
2.  \@Returns(\'NodeList\|HtmlCollection\')

</div>

[List](../../dart-core/list-class)\<[Node](../node-class)\>
getElementsByName(

1.  [String](../../dart-core/string-class) elementName

)

::: {.features}
\@Creates(\'NodeList\|HtmlCollection\'),
\@Returns(\'NodeList\|HtmlCollection\')
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Creates('NodeList|HtmlCollection')
@Returns('NodeList|HtmlCollection')
List<Node> getElementsByName(String elementName) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Document/getElementsByName.html>
:::

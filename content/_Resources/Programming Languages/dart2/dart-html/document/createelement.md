[dart:html](../../dart-html/dart-html-library){._links-link}

createElement method
====================

::: {.section .multi-line-signature}
[Element](../element-class) createElement(

1.  [String](../../dart-core/string-class) tagName,
2.  \[[String](../../dart-core/string-class)? typeExtension\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@pragma('dart2js:tryInline') // Almost all call sites have one argument.
Element createElement(String tagName, [String? typeExtension]) {
  return (typeExtension == null)
      ? _createElement_2(tagName)
      : _createElement(tagName, typeExtension);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Document/createElement.html>
:::

[dart:html](../../dart-html/dart-html-library){._links-link}

innerHtml property
==================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class)? innerHtml
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String? get innerHtml {
  final e = new DivElement();
  e.append(this.clone(true));
  return e.innerHtml;
}
```

::: {#setter .section .multi-line-signature}
void innerHtml=([String](../../dart-core/string-class)? value)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set innerHtml(String? value) {
  this.setInnerHtml(value);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/DocumentFragment/innerHtml.html>
:::

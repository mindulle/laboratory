[dart:svg](../../dart-svg/dart-svg-library){._links-link}

innerHtml property
==================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class)? innerHtml

::: {.features}
override
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String? get innerHtml {
  final container = new DivElement();
  final SvgElement cloned = this.clone(true) as SvgElement;
  container.children.addAll(cloned.children);
  return container.innerHtml;
}
```

::: {#setter .section .multi-line-signature}
void innerHtml=([String](../../dart-core/string-class)? value)

::: {.features}
override
:::
:::

Parses the HTML fragment and sets it as the contents of this element.

This uses the default sanitization behavior to sanitize the HTML
fragment, use [setInnerHtml](../../dart-html/element/setinnerhtml) to
override the default behavior.

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
<https://api.dart.dev/stable/2.18.5/dart-svg/SvgElement/innerHtml.html>
:::

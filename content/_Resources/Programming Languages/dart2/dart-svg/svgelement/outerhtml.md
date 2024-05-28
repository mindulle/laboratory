[dart:svg](../../dart-svg/dart-svg-library){._links-link}

outerHtml property
==================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class)? outerHtml

::: {.features}
override
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String? get outerHtml {
  final container = new DivElement();
  final SvgElement cloned = this.clone(true) as SvgElement;
  container.children.add(cloned);
  return container.innerHtml;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/SvgElement/outerHtml.html>
:::

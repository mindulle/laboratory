[dart:html](../../dart-html/dart-html-library){._links-link}

AnchorElement constructor
=========================

::: {.section .multi-line-signature}
AnchorElement(

1.  {[String](../../dart-core/string-class)? href}

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory AnchorElement({String? href}) {
  AnchorElement e = JS<AnchorElement>(
      'returns:AnchorElement;creates:AnchorElement;new:true',
      '#.createElement(#)',
      document,
      "a");
  if (href != null) e.href = href;
  return e;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/AnchorElement/AnchorElement.html>
:::

[dart:html](../../dart-html/dart-html-library){._links-link}

InputElement constructor
========================

::: {.section .multi-line-signature}
InputElement(

1.  {[String](../../dart-core/string-class)? type}

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory InputElement({String? type}) {
  InputElement e = document.createElement("input") as InputElement;
  if (type != null) {
    try {
      // IE throws an exception for unknown types.
      e.type = type;
    } catch (_) {}
  }
  return e;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/InputElement/InputElement.html>
:::

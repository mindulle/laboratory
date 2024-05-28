[dart:html](../../dart-html/dart-html-library){._links-link}

OptionElement constructor
=========================

::: {.section .multi-line-signature}
OptionElement(

1.  {[String](../../dart-core/string-class) data = \'\',
2.  [String](../../dart-core/string-class) value = \'\',
3.  [bool](../../dart-core/bool-class) selected = false}

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory OptionElement(
    {String data: '', String value: '', bool selected: false}) {
  return new OptionElement._(data, value, null, selected);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/OptionElement/OptionElement.html>
:::

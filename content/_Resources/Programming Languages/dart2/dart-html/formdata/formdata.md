[dart:html](../../dart-html/dart-html-library){._links-link}

FormData constructor
====================

::: {.section .multi-line-signature}
FormData(

1.  \[[FormElement](../formelement-class)? form\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory FormData([FormElement? form]) {
  if (form != null) {
    return FormData._create_1(form);
  }
  return FormData._create_2();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/FormData/FormData.html>
:::

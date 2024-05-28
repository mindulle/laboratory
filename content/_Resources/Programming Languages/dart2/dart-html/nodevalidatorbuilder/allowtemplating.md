[dart:html](../../dart-html/dart-html-library){._links-link}

allowTemplating method
======================

::: {.section .multi-line-signature}
void allowTemplating()
:::

Allow templating elements (such as and template-related attributes.

This still requires other validators to allow regular attributes to be
bound (such as [allowHtml5](allowhtml5)).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void allowTemplating() {
  add(new _TemplatingNodeValidator());
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/NodeValidatorBuilder/allowTemplating.html>
:::

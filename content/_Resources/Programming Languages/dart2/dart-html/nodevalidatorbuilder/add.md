[dart:html](../../dart-html/dart-html-library){._links-link}

add method
==========

::: {.section .multi-line-signature}
void add(

1.  [NodeValidator](../nodevalidator-class) validator

)
:::

Add an additional validator to the current list of validators.

Elements and attributes will be accepted if they are accepted by any
validators.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void add(NodeValidator validator) {
  _validators.add(validator);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/NodeValidatorBuilder/add.html>
:::

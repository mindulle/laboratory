[dart:svg](../../dart-svg/dart-svg-library){._links-link}

writeClasses method
===================

::: {.section .multi-line-signature}
void writeClasses(

1.  [Set](../../dart-core/set-class) s

)
:::

Join all the elements of a set into one string and write back to the
element. This is intended to be overridden by specific implementations.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void writeClasses(Set s) {
  _element.setAttribute('class', s.join(' '));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/AttributeClassSet/writeClasses.html>
:::

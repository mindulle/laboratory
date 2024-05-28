[dart:svg](../../dart-svg/dart-svg-library){._links-link}

removeAll method
================

::: {.section .multi-line-signature}
void removeAll(

1.  [Iterable](../../dart-core/iterable-class)\<[Object](../../dart-core/object-class)?\>
    iterable

)

::: {.features}
inherited
:::
:::

Remove all classes specified in `iterable` from element.

This is the Dart equivalent of jQuery\'s
[removeClass](http://api.jquery.com/removeClass/).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void removeAll(Iterable<Object?> iterable) {
  modify((s) => s.removeAll(iterable));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/AttributeClassSet/removeAll.html>
:::

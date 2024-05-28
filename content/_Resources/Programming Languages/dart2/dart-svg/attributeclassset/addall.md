[dart:svg](../../dart-svg/dart-svg-library){._links-link}

addAll method
=============

::: {.section .multi-line-signature}
void addAll(

1.  [Iterable](../../dart-core/iterable-class)\<[String](../../dart-core/string-class)\>
    iterable

)

::: {.features}
inherited
:::
:::

Add all classes specified in `iterable` to element.

This is the Dart equivalent of jQuery\'s
[addClass](http://api.jquery.com/addClass/).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void addAll(Iterable<String> iterable) {
  // TODO - see comment above about validation.
  modify((s) => s.addAll(iterable.map(_validateToken)));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/AttributeClassSet/addAll.html>
:::

[dart:svg](../../dart-svg/dart-svg-library){._links-link}

last property
=============

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) last

::: {.features}
inherited
:::
:::

Returns the last element.

Throws a [StateError](../../dart-core/stateerror-class) if `this` is
empty. Otherwise may iterate through the elements and returns the last
one seen. Some iterables may have more efficient ways to find the last
element (for example a list can directly access the last element,
without iterating through the previous ones).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get last => readClasses().last;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/AttributeClassSet/last.html>
:::

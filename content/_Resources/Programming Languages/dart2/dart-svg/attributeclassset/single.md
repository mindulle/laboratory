[dart:svg](../../dart-svg/dart-svg-library){._links-link}

single property
===============

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) single

::: {.features}
inherited
:::
:::

Checks that this iterable has only one element, and returns that
element.

Throws a [StateError](../../dart-core/stateerror-class) if `this` is
empty or has more than one element.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get single => readClasses().single;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/AttributeClassSet/single.html>
:::

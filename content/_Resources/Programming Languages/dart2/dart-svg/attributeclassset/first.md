[dart:svg](../../dart-svg/dart-svg-library){._links-link}

first property
==============

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) first

::: {.features}
inherited
:::
:::

Returns the first element.

Throws a [StateError](../../dart-core/stateerror-class) if `this` is
empty. Otherwise returns the first element in the iteration order,
equivalent to `this.elementAt(0)`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get first => readClasses().first;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/AttributeClassSet/first.html>
:::

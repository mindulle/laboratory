[dart:core](../../dart-core/dart-core-library){._links-link}

pattern property
================

::: {#getter .section .multi-line-signature}
[String](../string-class) pattern
:::

The source regular expression string used to create this `RegExp`.

``` {.language-dart data-language="dart"}
final regExp = RegExp(r'\p{L}');
print(regExp.pattern); // \p{L}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get pattern;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/RegExp/pattern.html>
:::

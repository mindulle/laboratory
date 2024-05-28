[dart:core](../../dart-core/dart-core-library){._links-link}

hasMatch method
===============

::: {.section .multi-line-signature}
[bool](../bool-class) hasMatch(

1.  [String](../string-class) input

)
:::

Whether the regular expression has a match in the string `input`.

``` {.language-dart data-language="dart"}
var string = 'Dash is a bird';
var regExp = RegExp(r'(humming)?bird');
var match = regExp.hasMatch(string); // true

regExp = RegExp(r'dog');
match = regExp.hasMatch(string); // false
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool hasMatch(String input);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/RegExp/hasMatch.html>
:::

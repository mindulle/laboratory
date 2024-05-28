[dart:core](../../dart-core/dart-core-library){._links-link}

stringMatch method
==================

::: {.section .multi-line-signature}
[String](../string-class)? stringMatch(

1.  [String](../string-class) input

)
:::

The substring of the first match of this regular expression in `input`.

``` {.language-dart data-language="dart"}
var string = 'Dash is a bird';
var regExp = RegExp(r'(humming)?bird');
var match = regExp.stringMatch(string); // Match

regExp = RegExp(r'dog');
match = regExp.stringMatch(string); // No match
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String? stringMatch(String input);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/RegExp/stringMatch.html>
:::

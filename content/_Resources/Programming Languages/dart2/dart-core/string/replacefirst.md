[dart:core](../../dart-core/dart-core-library){._links-link}

replaceFirst method
===================

::: {.section .multi-line-signature}
[String](../string-class) replaceFirst(

1.  [Pattern](../pattern-class) from,
2.  [String](../string-class) to,
3.  \[[int](../int-class) startIndex = 0\]

)
:::

Creates a new string with the first occurrence of `from` replaced by
`to`.

Finds the first match of `from` in this string, starting from
`startIndex`, and creates a new string where that match is replaced with
the `to` string.

Example:

``` {.language-dart data-language="dart"}
'0.0001'.replaceFirst(RegExp(r'0'), ''); // '.0001'
'0.0001'.replaceFirst(RegExp(r'0'), '7', 1); // '0.7001'
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String replaceFirst(Pattern from, String to, [int startIndex = 0]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/String/replaceFirst.html>
:::

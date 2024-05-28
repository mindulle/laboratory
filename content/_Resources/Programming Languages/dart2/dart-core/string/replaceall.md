[dart:core](../../dart-core/dart-core-library){._links-link}

replaceAll method
=================

::: {.section .multi-line-signature}
[String](../string-class) replaceAll(

1.  [Pattern](../pattern-class) from,
2.  [String](../string-class) replace

)
:::

Replaces all substrings that match `from` with `replace`.

Creates a new string in which the non-overlapping substrings matching
`from` (the ones iterated by `from.allMatches(thisString)`) are replaced
by the literal string `replace`.

``` {.language-dart data-language="dart"}
'resume'.replaceAll(RegExp(r'e'), 'é'); // 'résumé'
```

Notice that the `replace` string is not interpreted. If the replacement
depends on the match (for example, on a [RegExp](../regexp-class)\'s
capture groups), use the [replaceAllMapped](replaceallmapped) method
instead.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String replaceAll(Pattern from, String replace);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/String/replaceAll.html>
:::

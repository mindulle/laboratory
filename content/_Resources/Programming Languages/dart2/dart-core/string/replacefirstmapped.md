[dart:core](../../dart-core/dart-core-library){._links-link}

replaceFirstMapped method
=========================

::: {.section .multi-line-signature}
[String](../string-class) replaceFirstMapped(

1.  [Pattern](../pattern-class) from,
2.  [String](../string-class) replace(
    1.  [Match](../match-class) match

    ),
3.  \[[int](../int-class) startIndex = 0\]

)
:::

Replace the first occurrence of `from` in this string.

``` {.language-dart data-language="dart"}
const string = 'Dart is fun';
print(string.replaceFirstMapped(
    'fun', (m) => 'open source')); // Dart is open source

print(string.replaceFirstMapped(
    RegExp(r'\w(\w*)'), (m) => '<${m[0]}-${m[1]}>')); // <Dart-art> is fun
```

Returns a new string, which is this string except that the first match
of `from`, starting from `startIndex`, is replaced by the result of
calling `replace` with the match object.

The `startIndex` must be non-negative and no greater than
[length](length).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String replaceFirstMapped(Pattern from, String replace(Match match),
    [int startIndex = 0]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/String/replaceFirstMapped.html>
:::

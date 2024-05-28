[dart:core](../../dart-core/dart-core-library){._links-link}

startsWith method
=================

::: {.section .multi-line-signature}
[bool](../bool-class) startsWith(

1.  [Pattern](../pattern-class) pattern,
2.  \[[int](../int-class) index = 0\]

)
:::

Whether this string starts with a match of `pattern`.

``` {.language-dart data-language="dart"}
const string = 'Dart is open source';
print(string.startsWith('Dar')); // true
print(string.startsWith(RegExp(r'[A-Z][a-z]'))); // true
```

If `index` is provided, this method checks if the substring starting at
that index starts with a match of `pattern`:

``` {.language-dart data-language="dart"}
const string = 'Dart';
print(string.startsWith('art', 0)); // false
print(string.startsWith('art', 1)); // true
print(string.startsWith(RegExp(r'\w{3}'), 2)); // false
```

`index` must not be negative or greater than [length](length).

A [RegExp](../regexp-class) containing \'\^\' does not match if the
`index` is greater than zero and the regexp is not multi-line. The
pattern works on the string as a whole, and does not extract a substring
starting at `index` first:

``` {.language-dart data-language="dart"}
const string = 'Dart';
print(string.startsWith(RegExp(r'^art'), 1)); // false
print(string.startsWith(RegExp(r'art'), 1)); // true
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool startsWith(Pattern pattern, [int index = 0]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/String/startsWith.html>
:::

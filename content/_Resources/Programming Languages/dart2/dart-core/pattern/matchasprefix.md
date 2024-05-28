[dart:core](../../dart-core/dart-core-library){._links-link}

matchAsPrefix method
====================

::: {.section .multi-line-signature}
[Match](../match-class)? matchAsPrefix(

1.  [String](../string-class) string,
2.  \[[int](../int-class) start = 0\]

)
:::

Matches this pattern against the start of `string`.

Returns a match if the pattern matches a substring of `string` starting
at `start`, and `null` if the pattern doesn\'t match at that point.

The `start` must be non-negative and no greater than `string.length`.

``` {.language-dart data-language="dart"}
final string = 'Dash is a bird';

var regExp = RegExp(r'bird');
var match = regExp.matchAsPrefix(string, 10); // Match found.

regExp = RegExp(r'bird');
match = regExp.matchAsPrefix(string); // null
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Match? matchAsPrefix(String string, [int start = 0]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Pattern/matchAsPrefix.html>
:::

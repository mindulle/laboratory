[dart:core](../../dart-core/dart-core-library){._links-link}

allMatches method
=================

::: {.section .multi-line-signature}
[Iterable](../iterable-class)\<[RegExpMatch](../regexpmatch-class)\>
allMatches(

1.  [String](../string-class) input,
2.  \[[int](../int-class) start = 0\]

)

::: {.features}
override
:::
:::

Matches this pattern against the string repeatedly.

If `start` is provided, matching will start at that index.

The returned iterable lazily finds non-overlapping matches of the
pattern in the `string`. If a user only requests the first match, this
function should not compute all possible matches.

The matches are found by repeatedly finding the first match of the
pattern in the string, initially starting from `start`, and then from
the end of the previous match (but always at least one position later
than the *start* of the previous match, in case the pattern matches an
empty substring).

``` {.language-dart data-language="dart"}
RegExp exp = RegExp(r'(\w+)');
var str = 'Dash is a bird';
Iterable<Match> matches = exp.allMatches(str, 8);
for (final Match m in matches) {
  String match = m[0]!;
  print(match);
}
```

The output of the example is:

``` {.language-dart data-language="dart"}
a
bird
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Iterable<RegExpMatch> allMatches(String input, [int start = 0]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/RegExp/allMatches.html>
:::

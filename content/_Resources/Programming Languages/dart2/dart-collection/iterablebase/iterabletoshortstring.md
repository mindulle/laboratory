[dart:collection](../../dart-collection/dart-collection-library){._links-link}

iterableToShortString method
============================

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) iterableToShortString(

1.  [Iterable](../../dart-core/iterable-class) iterable,
2.  \[[String](../../dart-core/string-class) leftDelimiter = \'(\',
3.  [String](../../dart-core/string-class) rightDelimiter = \')\'\]

)
:::

Convert an `Iterable` to a string like
[IterableBase.toString](../../dart-core/iterable/tostring).

Allows using other delimiters than \'(\' and \')\'.

Handles circular references where converting one of the elements to a
string ends up converting `iterable` to a string again.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static String iterableToShortString(Iterable iterable,
    [String leftDelimiter = '(', String rightDelimiter = ')']) {
  if (_isToStringVisiting(iterable)) {
    if (leftDelimiter == "(" && rightDelimiter == ")") {
      // Avoid creating a new string in the "common" case.
      return "(...)";
    }
    return "$leftDelimiter...$rightDelimiter";
  }
  List<String> parts = <String>[];
  _toStringVisiting.add(iterable);
  try {
    _iterablePartsToStrings(iterable, parts);
  } finally {
    assert(identical(_toStringVisiting.last, iterable));
    _toStringVisiting.removeLast();
  }
  return (StringBuffer(leftDelimiter)
        ..writeAll(parts, ", ")
        ..write(rightDelimiter))
      .toString();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/IterableBase/iterableToShortString.html>
:::

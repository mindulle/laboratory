[dart:collection](../../dart-collection/dart-collection-library){._links-link}

iterableToFullString method
===========================

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) iterableToFullString(

1.  [Iterable](../../dart-core/iterable-class) iterable,
2.  \[[String](../../dart-core/string-class) leftDelimiter = \'(\',
3.  [String](../../dart-core/string-class) rightDelimiter = \')\'\]

)
:::

Converts an `Iterable` to a string.

Converts each elements to a string, and separates the results by \", \".
Then wraps the result in `leftDelimiter` and `rightDelimiter`.

Unlike [iterableToShortString](iterabletoshortstring), this conversion
doesn\'t omit any elements or puts any limit on the size of the result.

Handles circular references where converting one of the elements to a
string ends up converting `iterable` to a string again.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static String iterableToFullString(Iterable iterable,
    [String leftDelimiter = '(', String rightDelimiter = ')']) {
  if (_isToStringVisiting(iterable)) {
    return "$leftDelimiter...$rightDelimiter";
  }
  StringBuffer buffer = StringBuffer(leftDelimiter);
  _toStringVisiting.add(iterable);
  try {
    buffer.writeAll(iterable, ", ");
  } finally {
    assert(identical(_toStringVisiting.last, iterable));
    _toStringVisiting.removeLast();
  }
  buffer.write(rightDelimiter);
  return buffer.toString();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/IterableBase/iterableToFullString.html>
:::

[dart:core](../../dart-core/dart-core-library){._links-link}

RuneIterator.at constructor
===========================

::: {.section .multi-line-signature}
RuneIterator.at(

1.  [String](../string-class) string,
2.  [int](../int-class) index

)
:::

Create an iterator positioned before the `index`th code unit of the
string.

When created, there is no [current](current) value. A
[moveNext](movenext) will use the rune starting at `index` the current
value, and a [movePrevious](moveprevious) will use the rune ending just
before `index` as the current value.

The `index` position must not be in the middle of a surrogate pair.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
RuneIterator.at(String string, int index)
    : string = string,
      _position = index,
      _nextPosition = index {
  RangeError.checkValueInInterval(index, 0, string.length);
  _checkSplitSurrogate(index);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/RuneIterator/RuneIterator.at.html>
:::

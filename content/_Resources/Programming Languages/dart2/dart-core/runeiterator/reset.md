[dart:core](../../dart-core/dart-core-library){._links-link}

reset method
============

::: {.section .multi-line-signature}
void reset(

1.  \[[int](../int-class) rawIndex = 0\]

)
:::

Resets the iterator to the given index into the string.

After this the [current](current) value is unset. You must call
[moveNext](movenext) make the rune at the position current, or
[movePrevious](moveprevious) for the last rune before the position.

The `rawIndex` must be non-negative and no greater than `string.length`.
It must also not be the index of the trailing surrogate of a surrogate
pair.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void reset([int rawIndex = 0]) {
  RangeError.checkValueInInterval(rawIndex, 0, string.length, "rawIndex");
  _checkSplitSurrogate(rawIndex);
  _position = _nextPosition = rawIndex;
  _currentCodePoint = -1;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/RuneIterator/reset.html>
:::

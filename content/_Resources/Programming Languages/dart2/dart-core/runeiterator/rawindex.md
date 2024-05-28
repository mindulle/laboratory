[dart:core](../../dart-core/dart-core-library){._links-link}

rawIndex property
=================

::: {#getter .section .multi-line-signature}
[int](../int-class) rawIndex
:::

The starting position of the current rune in the string.

Returns -1 if there is no current rune ([current](current) is -1).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get rawIndex => (_position != _nextPosition) ? _position : -1;
```

::: {#setter .section .multi-line-signature}
void rawIndex=([int](../int-class) rawIndex)
:::

Resets the iterator to the rune at the specified index of the string.

Setting a negative [rawIndex](rawindex), or one greater than or equal to
`string.length`, is an error. So is setting it in the middle of a
surrogate pair.

Setting the position to the end of the string means that there is no
current rune.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void set rawIndex(int rawIndex) {
  RangeError.checkValidIndex(rawIndex, string, "rawIndex");
  reset(rawIndex);
  moveNext();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/RuneIterator/rawIndex.html>
:::

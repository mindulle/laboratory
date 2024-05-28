[dart:core](../../dart-core/dart-core-library){._links-link}

moveNext method
===============

::: {.section .multi-line-signature}
[bool](../bool-class) moveNext()

::: {.features}
override
:::
:::

Advances the iterator to the next element of the iteration.

Should be called before reading [current](current). If the call to
`moveNext` returns `true`, then [current](current) will contain the next
element of the iteration until `moveNext` is called again. If the call
returns `false`, there are no further elements and [current](current)
should not be used any more.

It is safe to call [moveNext](movenext) after it has already returned
`false`, but it must keep returning `false` and not have any other
effect.

A call to `moveNext` may throw for various reasons, including a
concurrent change to an underlying collection. If that happens, the
iterator may be in an inconsistent state, and any further behavior of
the iterator is unspecified, including the effect of reading
[current](current).

``` {.language-dart data-language="dart"}
final colors = ['blue', 'yellow', 'red'];
final colorsIterator = colors.iterator;
print(colorsIterator.moveNext()); // true
print(colorsIterator.moveNext()); // true
print(colorsIterator.moveNext()); // true
print(colorsIterator.moveNext()); // false
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool moveNext() {
  _position = _nextPosition;
  if (_position == string.length) {
    _currentCodePoint = -1;
    return false;
  }
  int codeUnit = string.codeUnitAt(_position);
  int nextPosition = _position + 1;
  if (_isLeadSurrogate(codeUnit) && nextPosition < string.length) {
    int nextCodeUnit = string.codeUnitAt(nextPosition);
    if (_isTrailSurrogate(nextCodeUnit)) {
      _nextPosition = nextPosition + 1;
      _currentCodePoint = _combineSurrogatePair(codeUnit, nextCodeUnit);
      return true;
    }
  }
  _nextPosition = nextPosition;
  _currentCodePoint = codeUnit;
  return true;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/RuneIterator/moveNext.html>
:::

[dart:core](../../dart-core/dart-core-library){._links-link}

movePrevious method
===================

::: {.section .multi-line-signature}
[bool](../bool-class) movePrevious()

::: {.features}
override
:::
:::

Move back to the previous element.

Returns true and updates [current](current) if successful. Returns false
and updates [current](current) to an implementation defined state if
there is no previous element

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool movePrevious() {
  _nextPosition = _position;
  if (_position == 0) {
    _currentCodePoint = -1;
    return false;
  }
  int position = _position - 1;
  int codeUnit = string.codeUnitAt(position);
  if (_isTrailSurrogate(codeUnit) && position > 0) {
    int prevCodeUnit = string.codeUnitAt(position - 1);
    if (_isLeadSurrogate(prevCodeUnit)) {
      _position = position - 1;
      _currentCodePoint = _combineSurrogatePair(prevCodeUnit, codeUnit);
      return true;
    }
  }
  _position = position;
  _currentCodePoint = codeUnit;
  return true;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/RuneIterator/movePrevious.html>
:::

[dart:core](../../dart-core/dart-core-library){._links-link}

last property
=============

::: {#getter .section .multi-line-signature}
[int](../int-class) last

::: {.features}
override
:::
:::

Returns the last element.

Throws a [StateError](../stateerror-class) if `this` is empty. Otherwise
may iterate through the elements and returns the last one seen. Some
iterables may have more efficient ways to find the last element (for
example a list can directly access the last element, without iterating
through the previous ones).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get last {
  if (string.length == 0) {
    throw StateError('No elements.');
  }
  int length = string.length;
  int code = string.codeUnitAt(length - 1);
  if (_isTrailSurrogate(code) && string.length > 1) {
    int previousCode = string.codeUnitAt(length - 2);
    if (_isLeadSurrogate(previousCode)) {
      return _combineSurrogatePair(previousCode, code);
    }
  }
  return code;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Runes/last.html>
:::

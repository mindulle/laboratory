[dart:core](../../dart-core/dart-core-library){._links-link}

currentAsString property
========================

::: {#getter .section .multi-line-signature}
[String](../string-class) currentAsString
:::

A string containing the current rune.

For runes outside the basic multilingual plane, this will be a String of
length 2, containing two code units.

Returns an empty string if there is no [current](current) value.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get currentAsString {
  if (_position == _nextPosition) return "";
  if (_position + 1 == _nextPosition) return string[_position];
  return string.substring(_position, _nextPosition);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/RuneIterator/currentAsString.html>
:::

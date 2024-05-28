[dart:convert](../../dart-convert/dart-convert-library){._links-link}

split method
============

::: {.section .multi-line-signature}
[Iterable](../../dart-core/iterable-class)\<[String](../../dart-core/string-class)\>
split(

1.  [String](../../dart-core/string-class) lines,
2.  \[[int](../../dart-core/int-class) start = 0,
3.  [int](../../dart-core/int-class)? end\]

)
:::

Split `lines` into individual lines.

If `start` and `end` are provided, only split the contents of
`lines.substring(start, end)`. The `start` and `end` values must specify
a valid sub-range of `lines` (`0 <= start <= end <= lines.length`).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Iterable<String> split(String lines, [int start = 0, int? end]) sync* {
  end = RangeError.checkValidRange(start, end, lines.length);
  var sliceStart = start;
  var char = 0;
  for (var i = start; i < end; i++) {
    var previousChar = char;
    char = lines.codeUnitAt(i);
    if (char != _CR) {
      if (char != _LF) continue;
      if (previousChar == _CR) {
        sliceStart = i + 1;
        continue;
      }
    }
    yield lines.substring(sliceStart, i);
    sliceStart = i + 1;
  }
  if (sliceStart < end) {
    yield lines.substring(sliceStart, end);
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/LineSplitter/split.html>
:::

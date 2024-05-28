[dart:convert](../../dart-convert/dart-convert-library){._links-link}

convert method
==============

::: {.section .multi-line-signature}
[List](../../dart-core/list-class)\<[String](../../dart-core/string-class)\>
convert(

1.  [String](../../dart-core/string-class) data

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
List<String> convert(String data) {
  var lines = <String>[];
  var end = data.length;
  var sliceStart = 0;
  var char = 0;
  for (var i = 0; i < end; i++) {
    var previousChar = char;
    char = data.codeUnitAt(i);
    if (char != _CR) {
      if (char != _LF) continue;
      if (previousChar == _CR) {
        sliceStart = i + 1;
        continue;
      }
    }
    lines.add(data.substring(sliceStart, i));
    sliceStart = i + 1;
  }
  if (sliceStart < end) {
    lines.add(data.substring(sliceStart, end));
  }
  return lines;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/LineSplitter/convert.html>
:::

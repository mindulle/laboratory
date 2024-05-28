[dart:web\_gl](../../dart-web_gl/dart-web_gl-library){._links-link}

getUniformIndices method
========================

::: {.section .multi-line-signature}
[List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>?
getUniformIndices(

1.  [Program](../program-class) program,
2.  [List](../../dart-core/list-class)\<[String](../../dart-core/string-class)\>
    uniformNames

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
List<int>? getUniformIndices(Program program, List<String> uniformNames) {
  List uniformNames_1 = convertDartToNative_StringArray(uniformNames);
  return _getUniformIndices_1(program, uniformNames_1);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_gl/RenderingContext2/getUniformIndices.html>
:::

[dart:html](../../dart-html/dart-html-library){._links-link}

define method
=============

::: {.section .multi-line-signature}
void define(

1.  [String](../../dart-core/string-class) name,
2.  [Object](../../dart-core/object-class) constructor,
3.  \[[Map](../../dart-core/map-class)? options\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void define(String name, Object constructor, [Map? options]) {
  if (options != null) {
    var options_1 = convertDartToNative_Dictionary(options);
    _define_1(name, constructor, options_1);
    return;
  }
  _define_2(name, constructor);
  return;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CustomElementRegistry/define.html>
:::

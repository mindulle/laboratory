[dart:html](../../dart-html/dart-html-library){._links-link}

HashChangeEvent constructor
===========================

::: {.section .multi-line-signature}
HashChangeEvent(

1.  [String](../../dart-core/string-class) type,
2.  {[bool](../../dart-core/bool-class) canBubble = true,
3.  [bool](../../dart-core/bool-class) cancelable = true,
4.  [String](../../dart-core/string-class)? oldUrl,
5.  [String](../../dart-core/string-class)? newUrl}

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory HashChangeEvent(String type,
    {bool canBubble: true,
    bool cancelable: true,
    String? oldUrl,
    String? newUrl}) {
  var options = {
    'canBubble': canBubble,
    'cancelable': cancelable,
    'oldURL': oldUrl,
    'newURL': newUrl,
  };
  return JS('HashChangeEvent', 'new HashChangeEvent(#, #)', type,
      convertDartToNative_Dictionary(options));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/HashChangeEvent/HashChangeEvent.html>
:::

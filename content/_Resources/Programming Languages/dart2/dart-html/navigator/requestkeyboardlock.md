[dart:html](../../dart-html/dart-html-library){._links-link}

requestKeyboardLock method
==========================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) requestKeyboardLock(

1.  \[[List](../../dart-core/list-class)\<[String](../../dart-core/string-class)\>?
    keyCodes\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future requestKeyboardLock([List<String>? keyCodes]) {
  if (keyCodes != null) {
    List keyCodes_1 = convertDartToNative_StringArray(keyCodes);
    return _requestKeyboardLock_1(keyCodes_1);
  }
  return _requestKeyboardLock_2();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Navigator/requestKeyboardLock.html>
:::

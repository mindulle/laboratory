[dart:html](../../dart-html/dart-html-library){._links-link}

set method
==========

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) set(

1.  [String](../../dart-core/string-class) name,
2.  [String](../../dart-core/string-class) value,
3.  \[[Map](../../dart-core/map-class)? options\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future set(String name, String value, [Map? options]) {
  var options_dict = null;
  if (options != null) {
    options_dict = convertDartToNative_Dictionary(options);
  }
  return promiseToFuture(
      JS("", "#.set(#, #, #)", this, name, value, options_dict));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CookieStore/set.html>
:::

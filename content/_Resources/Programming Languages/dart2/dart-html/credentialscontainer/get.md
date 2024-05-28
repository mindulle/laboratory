[dart:html](../../dart-html/dart-html-library){._links-link}

get method
==========

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) get(

1.  \[[Map](../../dart-core/map-class)? options\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future get([Map? options]) {
  var options_dict = null;
  if (options != null) {
    options_dict = convertDartToNative_Dictionary(options);
  }
  return promiseToFuture(
      JS("creates:Credential;", "#.get(#)", this, options_dict));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CredentialsContainer/get.html>
:::

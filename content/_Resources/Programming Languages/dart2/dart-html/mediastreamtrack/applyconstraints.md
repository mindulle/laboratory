[dart:html](../../dart-html/dart-html-library){._links-link}

applyConstraints method
=======================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) applyConstraints(

1.  \[[Map](../../dart-core/map-class)? constraints\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future applyConstraints([Map? constraints]) {
  var constraints_dict = null;
  if (constraints != null) {
    constraints_dict = convertDartToNative_Dictionary(constraints);
  }
  return promiseToFuture(
      JS("", "#.applyConstraints(#)", this, constraints_dict));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MediaStreamTrack/applyConstraints.html>
:::

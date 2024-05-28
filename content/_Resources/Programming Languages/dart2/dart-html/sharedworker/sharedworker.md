[dart:html](../../dart-html/dart-html-library){._links-link}

SharedWorker constructor
========================

::: {.section .multi-line-signature}
SharedWorker(

1.  [String](../../dart-core/string-class) scriptURL,
2.  \[[String](../../dart-core/string-class)? name\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory SharedWorker(String scriptURL, [String? name]) {
  if (name != null) {
    return SharedWorker._create_1(scriptURL, name);
  }
  return SharedWorker._create_2(scriptURL);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/SharedWorker/SharedWorker.html>
:::

[dart:html](../../dart-html/dart-html-library){._links-link}

store method
============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) store(

1.  [Credential](../credential-class) credential

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future store(Credential credential) => promiseToFuture(
    JS("creates:Credential;", "#.store(#)", this, credential));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CredentialsContainer/store.html>
:::

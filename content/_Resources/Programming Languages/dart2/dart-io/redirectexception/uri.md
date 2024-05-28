[dart:io](../../dart-io/dart-io-library){._links-link}

uri property
============

::: {#getter .section .multi-line-signature}
[Uri](../../dart-core/uri-class)? uri

::: {.features}
override
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Uri? get uri => redirects.isEmpty ? null : redirects.last.location;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RedirectException/uri.html>
:::

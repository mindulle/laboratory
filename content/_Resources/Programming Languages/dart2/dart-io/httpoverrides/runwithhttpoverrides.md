[dart:io](../../dart-io/dart-io-library){._links-link}

runWithHttpOverrides\<R\> method
================================

::: {.section .multi-line-signature}
R runWithHttpOverrides\<R\>(

1.  R body( ),
2.  [HttpOverrides](../httpoverrides-class) overrides

)
:::

Runs `body` in a fresh [Zone](../../dart-async/zone-class) using the
overrides found in `overrides`.

Note that `overrides` should be an instance of a class that extends
[HttpOverrides](../httpoverrides-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static R runWithHttpOverrides<R>(R Function() body, HttpOverrides overrides) {
  return _asyncRunZoned<R>(body,
      zoneValues: {_httpOverridesToken: overrides});
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpOverrides/runWithHttpOverrides.html>
:::

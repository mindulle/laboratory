[dart:io](../../dart-io/dart-io-library){._links-link}

environment property
====================

::: {#getter .section .multi-line-signature}
[Map](../../dart-core/map-class)\<[String](../../dart-core/string-class),
[String](../../dart-core/string-class)\> environment
:::

The environment for this process as a map from string key to string
value.

The map is unmodifiable, and its content is retrieved from the operating
system on its first use.

Environment variables on Windows are case-insensitive, so on Windows the
map is case-insensitive and will convert all keys to upper case. On
other platforms, keys can be distinguished by case.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Map<String, String> get environment => _Platform.environment;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Platform/environment.html>
:::

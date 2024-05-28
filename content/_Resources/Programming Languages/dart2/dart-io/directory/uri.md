[dart:io](../../dart-io/dart-io-library){._links-link}

uri property
============

::: {#getter .section .multi-line-signature}
[Uri](../../dart-core/uri-class) uri

::: {.features}
override
:::
:::

A [Uri](../../dart-core/uri-class) representing the directory\'s
location.

The URI\'s scheme is always \"file\" if the entity\'s [path](path) is
absolute, otherwise the scheme will be empty and the URI relative. The
URI\'s path always ends in a slash (\'/\').

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Uri get uri;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Directory/uri.html>
:::

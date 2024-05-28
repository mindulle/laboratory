[dart:io](../../dart-io/dart-io-library){._links-link}

maxConnectionsPerHost property
==============================

::: {.section .multi-line-signature}
[int](../../dart-core/int-class)? maxConnectionsPerHost

::: {.features}
read / write
:::
:::

Gets and sets the maximum number of live connections, to a single host.

Increasing this number may lower performance and take up unwanted system
resources.

To disable, set to `null`.

Default is `null`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int? maxConnectionsPerHost;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClient/maxConnectionsPerHost.html>
:::

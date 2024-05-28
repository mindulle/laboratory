[dart:io](../../dart-io/dart-io-library){._links-link}

findProxy property
==================

::: {#setter .section .multi-line-signature}
void findProxy=([String](../../dart-core/string-class)
f([Uri](../../dart-core/uri-class) url)?)
:::

Sets the function used to resolve the proxy server to be used for
opening a HTTP connection to the specified `url`. If this function is
not set, direct connections will always be used.

The string returned by `f` must be in the format used by browser PAC
(proxy auto-config) scripts. That is either

``` {.language-dart data-language="dart"}
"DIRECT"
```

for using a direct connection or

``` {.language-dart data-language="dart"}
"PROXY host:port"
```

for using the proxy server `host` on port `port`.

A configuration can contain several configuration elements separated by
semicolons, e.g.

``` {.language-dart data-language="dart"}
"PROXY host:port; PROXY host2:port2; DIRECT"
```

The static function [findProxyFromEnvironment](findproxyfromenvironment)
on this class can be used to implement proxy server resolving based on
environment variables.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void set findProxy(String Function(Uri url)? f);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClient/findProxy.html>
:::

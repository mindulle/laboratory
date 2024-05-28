[dart:io](../../dart-io/dart-io-library){._links-link}

findProxyFromEnvironment method
===============================

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) findProxyFromEnvironment(

1.  [Uri](../../dart-core/uri-class) url,
2.  {[Map](../../dart-core/map-class)\<[String](../../dart-core/string-class),
    [String](../../dart-core/string-class)\>? environment}

)
:::

Function for resolving the proxy server to be used for a HTTP connection
from the proxy configuration specified through environment variables.

The following environment variables are taken into account:

``` {.language-dart data-language="dart"}
http_proxy
https_proxy
no_proxy
HTTP_PROXY
HTTPS_PROXY
NO_PROXY
```

`http_proxy` and `HTTP_PROXY` specify the proxy server to use for
http:// urls. Use the format `hostname:port`. If no port is used a
default of 1080 will be used. If both are set the lower case one takes
precedence.

`https_proxy` and `HTTPS_PROXY` specify the proxy server to use for
https:// urls. Use the format `hostname:port`. If no port is used a
default of 1080 will be used. If both are set the lower case one takes
precedence.

`no_proxy` and `NO_PROXY` specify a comma separated list of postfixes of
hostnames for which not to use the proxy server. E.g. the value
\"localhost,127.0.0.1\" will make requests to both \"localhost\" and
\"127.0.0.1\" not use a proxy. If both are set the lower case one takes
precedence.

To activate this way of resolving proxies assign this function to the
[findProxy](findproxy) property on the
[HttpClient](../httpclient-class).

``` {.language-dart data-language="dart"}
HttpClient client = HttpClient();
client.findProxy = HttpClient.findProxyFromEnvironment;
```

If you don\'t want to use the system environment you can use a different
one by wrapping the function.

``` {.language-dart data-language="dart"}
HttpClient client = HttpClient();
client.findProxy = (url) {
  return HttpClient.findProxyFromEnvironment(
      url, environment: {"http_proxy": ..., "no_proxy": ...});
}
```

If a proxy requires authentication it is possible to configure the
username and password as well. Use the format
`username:password@hostname:port` to include the username and password.
Alternatively the API [addProxyCredentials](addproxycredentials) can be
used to set credentials for proxies which require authentication.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static String findProxyFromEnvironment(Uri url,
    {Map<String, String>? environment}) {
  HttpOverrides? overrides = HttpOverrides.current;
  if (overrides == null) {
    return _HttpClient._findProxyFromEnvironment(url, environment);
  }
  return overrides.findProxyFromEnvironment(url, environment);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClient/findProxyFromEnvironment.html>
:::

[dart:io](../../dart-io/dart-io-library){._links-link}

connectionFactory property
==========================

::: {#setter .section .multi-line-signature}
void
connectionFactory=([Future](../../dart-async/future-class)\<[ConnectionTask](../connectiontask-class)\<[Socket](../socket-class)\>\>
f([Uri](../../dart-core/uri-class) url,
[String](../../dart-core/string-class)? proxyHost,
[int](../../dart-core/int-class)? proxyPort)?)
:::

Sets the function used to create socket connections.

The URL requested (e.g. through [getUrl](geturl)) and proxy
configuration (`f.proxyHost` and `f.proxyPort`) are passed as arguments.
`f.proxyHost` and `f.proxyPort` will be `null` if the connection is not
made through a proxy.

Since connections may be reused based on host and port, it is important
that the function not ignore `f.proxyHost` and `f.proxyPort` if they are
not `null`. If proxies are not meaningful for the returned
[Socket](../socket-class), you can set [findProxy](findproxy) to use a
direct connection.

For example:

``` {.language-dart data-language="dart"}
import "dart:io";

void main() async {
  HttpClient client = HttpClient()
    ..connectionFactory = (Uri uri, String? proxyHost, int? proxyPort) {
        assert(proxyHost == null);
        assert(proxyPort == null);
        var address = InternetAddress("/var/run/docker.sock",
            type: InternetAddressType.unix);
        return Socket.startConnect(address, 0);
    }
    ..findProxy = (Uri uri) => 'DIRECT';

  final request = await client.getUrl(Uri.parse("http://ignored/v1.41/info"));
  final response = await request.close();
  print(response.statusCode);
  await response.drain();
  client.close();
}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void set connectionFactory(
    Future<ConnectionTask<Socket>> Function(
            Uri url, String? proxyHost, int? proxyPort)?
        f);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClient/connectionFactory.html>
:::

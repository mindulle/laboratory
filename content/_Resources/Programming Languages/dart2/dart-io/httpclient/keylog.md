[dart:io](../../dart-io/dart-io-library){._links-link}

keyLog property
===============

::: {#setter .section .multi-line-signature}
void keyLog=(dynamic callback([String](../../dart-core/string-class)
line)?)
:::

Sets a callback that will be called when new TLS keys are exchanged with
the server. It will receive one line of text in [NSS Key Log
Format](https://developer.mozilla.org/en-US/docs/Mozilla/Projects/NSS/Key_Log_Format)
for each call. Writing these lines to a file will allow tools (such as
[Wireshark](https://gitlab.com/wireshark/wireshark/-/wikis/TLS#tls-decryption))
to decrypt communication between the this client and the server. This is
meant to allow network-level debugging of secure sockets and should not
be used in production code. For example:

``` {.language-dart data-language="dart"}
final log = File('keylog.txt');
final client = HttpClient();
client.keyLog = (line) => log.writeAsStringSync(line,
    mode: FileMode.append);
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void set keyLog(Function(String line)? callback);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClient/keyLog.html>
:::

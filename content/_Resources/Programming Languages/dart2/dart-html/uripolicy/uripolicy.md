[dart:html](../../dart-html/dart-html-library){._links-link}

UriPolicy constructor
=====================

::: {.section .multi-line-signature}
UriPolicy()
:::

Constructs the default UriPolicy which is to only allow Uris to the same
origin as the application was launched from.

This will block all ftp: mailto: URIs. It will also block accessing
<https://example.com> if the app is running from <http://example.com>.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory UriPolicy() => new _SameOriginUriPolicy();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/UriPolicy/UriPolicy.html>
:::

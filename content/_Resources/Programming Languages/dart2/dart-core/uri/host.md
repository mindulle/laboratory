[dart:core](../../dart-core/dart-core-library){._links-link}

host property
=============

::: {#getter .section .multi-line-signature}
[String](../string-class) host
:::

The host part of the authority component.

The value is the empty string if there is no authority component and
hence no host.

If the host is an IP version 6 address, the surrounding `[` and `]` is
removed.

The host string is case-insensitive. The returned host name is
canonicalized to lower-case with upper-case percent-escapes.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get host;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Uri/host.html>
:::

[dart:io](../../dart-io/dart-io-library){._links-link}

defaultContext property
=======================

::: {#getter .section .multi-line-signature}
[SecurityContext](../securitycontext-class) defaultContext
:::

The default security context used by most operation requiring one.

Secure networking classes with an optional `context` parameter use the
[defaultContext](defaultcontext) object if the parameter is omitted.
This object can also be accessed, and modified, directly. Each isolate
has a different [defaultContext](defaultcontext) object. The
[defaultContext](defaultcontext) object uses a list of well-known
trusted certificate authorities as its trusted roots. On Linux and
Windows, this list is taken from Mozilla, who maintains it as part of
Firefox. On, MacOS, iOS, and Android, this list comes from the trusted
certificates stores built in to the platforms.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external static SecurityContext get defaultContext;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/SecurityContext/defaultContext.html>
:::

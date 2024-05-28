[dart:io](../../dart-io/dart-io-library){._links-link}

SecurityContext constructor
===========================

::: {.section .multi-line-signature}
SecurityContext(

1.  {[bool](../../dart-core/bool-class) withTrustedRoots = false}

)
:::

Creates a new [SecurityContext](../securitycontext-class).

By default, the created [SecurityContext](../securitycontext-class)
contains no keys or certificates. These can be added by calling the
methods of this class.

If `withTrustedRoots` is passed as `true`, the
[SecurityContext](../securitycontext-class) will be seeded by the
trusted root certificates provided as explained below. To obtain a
[SecurityContext](../securitycontext-class) containing trusted root
certificates, [SecurityContext.defaultContext](defaultcontext) is
usually sufficient, and should be used instead. However, if the
[SecurityContext](../securitycontext-class) containing the trusted root
certificates must be modified per-connection, then `withTrustedRoots`
should be used.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory SecurityContext({bool withTrustedRoots = false});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/SecurityContext/SecurityContext.html>
:::

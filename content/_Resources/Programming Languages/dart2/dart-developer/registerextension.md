[dart:developer](../dart-developer/dart-developer-library){._links-link}

registerExtension function
==========================

::: {.section .multi-line-signature}
void registerExtension(

1.  [String](../dart-core/string-class) method,
2.  [ServiceExtensionHandler](serviceextensionhandler) handler

)
:::

Register a [ServiceExtensionHandler](serviceextensionhandler) that will
be invoked in this isolate for `method`. *NOTE*: Service protocol
extensions must be registered in each isolate.

*NOTE*: `method` must begin with \'ext.\' and you should use the
following structure to avoid conflicts with other packages:
\'ext.package.command\'. That is, immediately following the \'ext.\'
prefix, should be the registering package name followed by another
period (\'.\') and then the command name. For example:
\'ext.dart.io.getOpenFiles\'.

Because service extensions are isolate specific, clients using
extensions must always include an \'isolateId\' parameter with each RPC.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void registerExtension(String method, ServiceExtensionHandler handler) {
  // TODO: When NNBD is complete, delete the following line.
  checkNotNullable(method, 'method');
  if (!method.startsWith('ext.')) {
    throw new ArgumentError.value(method, 'method', 'Must begin with ext.');
  }
  if (_lookupExtension(method) != null) {
    throw new ArgumentError('Extension already registered: $method');
  }
  // TODO: When NNBD is complete, delete the following line.
  checkNotNullable(handler, 'handler');
  _registerExtension(method, handler);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/registerExtension.html>
:::

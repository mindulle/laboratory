[dart:html](../../dart-html/dart-html-library){._links-link}

query method
============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[PermissionStatus](../permissionstatus-class)\>
query(

1.  [Map](../../dart-core/map-class) permission

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<PermissionStatus> query(Map permission) {
  var permission_dict = convertDartToNative_Dictionary(permission);
  return promiseToFuture<PermissionStatus>(
      JS("creates:PermissionStatus;", "#.query(#)", this, permission_dict));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Permissions/query.html>
:::

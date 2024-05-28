[dart:html](../../dart-html/dart-html-library){._links-link}

request method
==============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[PermissionStatus](../permissionstatus-class)\>
request(

1.  [Map](../../dart-core/map-class) permissions

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<PermissionStatus> request(Map permissions) {
  var permissions_dict = convertDartToNative_Dictionary(permissions);
  return promiseToFuture<PermissionStatus>(JS(
      "creates:PermissionStatus;", "#.request(#)", this, permissions_dict));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Permissions/request.html>
:::

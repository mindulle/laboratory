[dart:html](../../dart-html/dart-html-library){._links-link}

requestAll method
=================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[PermissionStatus](../permissionstatus-class)\>
requestAll(

1.  [List](../../dart-core/list-class)\<[Map](../../dart-core/map-class)\>
    permissions

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<PermissionStatus> requestAll(List<Map> permissions) =>
    promiseToFuture<PermissionStatus>(JS(
        "creates:PermissionStatus;", "#.requestAll(#)", this, permissions));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Permissions/requestAll.html>
:::

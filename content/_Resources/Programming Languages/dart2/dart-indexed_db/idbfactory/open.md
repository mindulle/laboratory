[dart:indexed\_db](../../dart-indexed_db/dart-indexed_db-library){._links-link}

open method
===========

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[Database](../database-class)\>
open(

1.  [String](../../dart-core/string-class) name,
2.  {[int](../../dart-core/int-class)? version,
3.  void onUpgradeNeeded(
    1.  [VersionChangeEvent](../versionchangeevent-class) event

    )?,
4.  void onBlocked(
    1.  [Event](../../dart-html/event-class) event

    )?}

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<Database> open(String name,
    {int? version,
    void onUpgradeNeeded(VersionChangeEvent event)?,
    void onBlocked(Event event)?}) {
  if ((version == null) != (onUpgradeNeeded == null)) {
    return new Future.error(new ArgumentError(
        'version and onUpgradeNeeded must be specified together'));
  }
  try {
    OpenDBRequest request;
    if (version != null) {
      request = _open(name, version);
    } else {
      request = _open(name);
    }

    if (onUpgradeNeeded != null) {
      request.onUpgradeNeeded.listen(onUpgradeNeeded);
    }
    if (onBlocked != null) {
      request.onBlocked.listen(onBlocked);
    }
    return _completeRequest(request);
  } catch (e, stacktrace) {
    return new Future.error(e, stacktrace);
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-indexed_db/IdbFactory/open.html>
:::

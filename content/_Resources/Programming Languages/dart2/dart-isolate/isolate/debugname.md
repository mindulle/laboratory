[dart:isolate](../../dart-isolate/dart-isolate-library){._links-link}

debugName property
==================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class)? debugName

::: {.features}
\@Since(\"2.3\")
:::
:::

The name of the [Isolate](../isolate-class) displayed for debug
purposes.

This can be set using the `debugName` parameter in [spawn](spawn) and
[spawnUri](spawnuri).

This name does not uniquely identify an isolate. Multiple isolates in
the same process may have the same `debugName`.

For a given isolate, this value will be the same as the values returned
by `Dart_DebugName` in the C embedding API and the `debugName` property
in [IsolateMirror](../../dart-mirrors/isolatemirror-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Since("2.3")
external String? get debugName;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-isolate/Isolate/debugName.html>
:::

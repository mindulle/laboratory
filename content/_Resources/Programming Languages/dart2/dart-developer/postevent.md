[dart:developer](../dart-developer/dart-developer-library){._links-link}

postEvent function
==================

::: {.section .multi-line-signature}
void postEvent(

1.  [String](../dart-core/string-class) eventKind,
2.  [Map](../dart-core/map-class) eventData

)
:::

Post an event of `eventKind` with payload of `eventData` to the
\"Extension\" event stream.

If [extensionStreamHasListener](extensionstreamhaslistener) is false,
this method is a no-op.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void postEvent(String eventKind, Map eventData) {
  if (!extensionStreamHasListener) {
    return;
  }
  // TODO: When NNBD is complete, delete the following two lines.
  checkNotNullable(eventKind, 'eventKind');
  checkNotNullable(eventData, 'eventData');
  String eventDataAsString = json.encode(eventData);
  _postEvent(eventKind, eventDataAsString);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/postEvent.html>
:::

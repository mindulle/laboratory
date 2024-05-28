[dart:html](../../dart-html/dart-html-library){._links-link}

MessageEvent constructor
========================

::: {.section .multi-line-signature}
MessageEvent(

1.  [String](../../dart-core/string-class) type,
2.  {[bool](../../dart-core/bool-class) canBubble = false,
3.  [bool](../../dart-core/bool-class) cancelable = false,
4.  [Object](../../dart-core/object-class)? data,
5.  [String](../../dart-core/string-class)? origin,
6.  [String](../../dart-core/string-class)? lastEventId,
7.  [Window](../window-class)? source,
8.  [List](../../dart-core/list-class)\<[MessagePort](../messageport-class)\>
    messagePorts = const \[\]}

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory MessageEvent(String type,
    {bool canBubble: false,
    bool cancelable: false,
    Object? data,
    String? origin,
    String? lastEventId,
    Window? source,
    List<MessagePort> messagePorts: const []}) {
  if (source == null) {
    source = window;
  }
  if (!Device.isIE) {
    // TODO: This if check should be removed once IE
    // implements the constructor.
    return JS(
        'MessageEvent',
        'new MessageEvent(#, {bubbles: #, cancelable: #, data: #, origin: #, lastEventId: #, source: #, ports: #})',
        type,
        canBubble,
        cancelable,
        data,
        origin,
        lastEventId,
        source,
        messagePorts);
  }
  MessageEvent event = document._createEvent("MessageEvent") as MessageEvent;
  event._initMessageEvent(type, canBubble, cancelable, data, origin,
      lastEventId, source, messagePorts);
  return event;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MessageEvent/MessageEvent.html>
:::

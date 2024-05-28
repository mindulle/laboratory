[dart:html](../../dart-html/dart-html-library){._links-link}

dragEvent constant
==================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[MouseEvent](../mouseevent-class)\>
const dragEvent
:::

A stream of `drag` events fired when an element is currently being
dragged.

A `drag` event is added to this stream as soon as the drag begins. A
`drag` event is also added to this stream at intervals while the drag
operation is still ongoing.

Other resources
---------------

-   [Drag and drop
    sample](https://github.com/dart-lang/dart-samples/tree/master/html5/web/dnd/basics)
    based on [the
    tutorial](http://www.html5rocks.com/en/tutorials/dnd/basics/) from
    HTML5Rocks.
-   [Drag and drop
    specification](https://html.spec.whatwg.org/multipage/interaction.html#dnd)
    from WHATWG.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static const EventStreamProvider<MouseEvent> dragEvent =
    const EventStreamProvider<MouseEvent>('drag');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/dragEvent-constant.html>
:::

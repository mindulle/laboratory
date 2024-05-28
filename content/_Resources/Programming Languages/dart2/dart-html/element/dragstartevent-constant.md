[dart:html](../../dart-html/dart-html-library){._links-link}

dragStartEvent constant
=======================

::: {.section .multi-line-signature}
[EventStreamProvider](../eventstreamprovider-class)\<[MouseEvent](../mouseevent-class)\>
const dragStartEvent
:::

A stream of `dragstart` events for a dragged element whose drag has
begun.

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
static const EventStreamProvider<MouseEvent> dragStartEvent =
    const EventStreamProvider<MouseEvent>('dragstart');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/dragStartEvent-constant.html>
:::

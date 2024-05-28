[dart:svg](../../dart-svg/dart-svg-library){._links-link}

dragEnterEvent constant
=======================

::: {.section .multi-line-signature}
[EventStreamProvider](../../dart-html/eventstreamprovider-class)\<[MouseEvent](../../dart-html/mouseevent-class)\>
const dragEnterEvent
:::

A stream of `dragenter` events fired when a dragged object is first
dragged over an element.

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
static const EventStreamProvider<MouseEvent> dragEnterEvent =
    const EventStreamProvider<MouseEvent>('dragenter');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/SvgElement/dragEnterEvent-constant.html>
:::

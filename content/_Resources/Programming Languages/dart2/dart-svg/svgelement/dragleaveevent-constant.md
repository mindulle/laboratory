[dart:svg](../../dart-svg/dart-svg-library){._links-link}

dragLeaveEvent constant
=======================

::: {.section .multi-line-signature}
[EventStreamProvider](../../dart-html/eventstreamprovider-class)\<[MouseEvent](../../dart-html/mouseevent-class)\>
const dragLeaveEvent
:::

A stream of `dragleave` events fired when an object being dragged over
an element leaves the element\'s target area.

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
static const EventStreamProvider<MouseEvent> dragLeaveEvent =
    const EventStreamProvider<MouseEvent>('dragleave');
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/SvgElement/dragLeaveEvent-constant.html>
:::

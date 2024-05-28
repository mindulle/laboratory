[dart:svg](../../dart-svg/dart-svg-library){._links-link}

onDragEnter property
====================

::: {#getter .section .multi-line-signature}
[ElementStream](../../dart-html/elementstream-class)\<[MouseEvent](../../dart-html/mouseevent-class)\>
onDragEnter

::: {.features}
override
:::
:::

A stream of `dragenter` events fired when a dragged object is first
dragged over this element.

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
ElementStream<MouseEvent> get onDragEnter => dragEnterEvent.forElement(this);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/SvgElement/onDragEnter.html>
:::

[dart:html](../../dart-html/dart-html-library){._links-link}

offsetTo method
===============

::: {.section .multi-line-signature}
[Point](../../dart-math/point-class)\<[num](../../dart-core/num-class)\>
offsetTo(

1.  [Element](../element-class) parent

)
:::

Provides the offset of this element\'s [borderEdge](borderedge) relative
to the specified `parent`.

This is the Dart equivalent of jQuery\'s
[position](http://api.jquery.com/position/) method. Unlike jQuery\'s
position, however, `parent` can be any parent element of `this`, rather
than only `this`\'s immediate [offsetParent](offsetparent). If the
specified element is *not* an offset parent or transitive offset parent
to this element, an [ArgumentError](../../dart-core/argumenterror-class)
is thrown.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Point offsetTo(Element parent) {
  return Element._offsetToHelper(this, parent);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/offsetTo.html>
:::

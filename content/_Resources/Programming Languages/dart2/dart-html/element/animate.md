[dart:html](../../dart-html/dart-html-library){._links-link}

animate method
==============

::: {.section .multi-line-signature}
<div>

1.  \@SupportedBrowser(SupportedBrowser.CHROME, \'36\')

</div>

[Animation](../animation-class) animate(

1.  [Iterable](../../dart-core/iterable-class)\<[Map](../../dart-core/map-class)\<[String](../../dart-core/string-class),
    dynamic\>\> frames,
2.  \[dynamic timing\]

)

::: {.features}
\@SupportedBrowser(SupportedBrowser.CHROME, \'36\')
:::
:::

Creates a new AnimationEffect object whose target element is the object
on which the method is called, and calls the play() method of the
AnimationTimeline object of the document timeline of the node document
of the element, passing the newly created AnimationEffect as the
argument to the method. Returns an Animation for the effect.

Examples

``` {.language-dart data-language="dart"}
var animation = elem.animate([{"opacity": 75}, {"opacity": 0}], 200);

var animation = elem.animate([
  {"transform": "translate(100px, -100%)"},
  {"transform" : "translate(400px, 500px)"}
], 1500);
```

The `frames` parameter is an Iterable, where the map entries specify CSS
animation effects. The `timing` parameter can be a double, representing
the number of milliseconds for the transition, or a Map with fields
corresponding to those of the `timing` object.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@SupportedBrowser(SupportedBrowser.CHROME, '36')
Animation animate(Iterable<Map<String, dynamic>> frames, [timing]) {
  if (frames is! Iterable || !(frames.every((x) => x is Map))) {
    throw new ArgumentError("The frames parameter should be a List of Maps "
        "with frame information");
  }
  var convertedFrames;
  if (frames is Iterable) {
    convertedFrames = frames.map(convertDartToNative_Dictionary).toList();
  } else {
    convertedFrames = frames;
  }
  var convertedTiming =
      timing is Map ? convertDartToNative_Dictionary(timing) : timing;
  return convertedTiming == null
      ? _animate(convertedFrames)
      : _animate(convertedFrames, convertedTiming);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/animate.html>
:::

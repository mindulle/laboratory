[dart:html](../../dart-html/dart-html-library){._links-link}

scrollY property
================

::: {#getter .section .multi-line-signature}
[int](../../dart-core/int-class) scrollY
:::

The distance this window has been scrolled vertically.

Other resources
---------------

-   [The Screen interface
    specification](http://www.w3.org/TR/cssom-view/#screen) from W3C.
-   [scrollY](https://developer.mozilla.org/en-US/docs/Web/API/Window.scrollY)
    from MDN.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get scrollY => JS<bool>('bool', '("scrollY" in #)', this)
    ? JS<num>('num', '#.scrollY', this).round()
    : document.documentElement!.scrollTop;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Window/scrollY.html>
:::

[dart:html](../../dart-html/dart-html-library){._links-link}

scrollIntoView method
=====================

::: {.section .multi-line-signature}
void scrollIntoView(

1.  \[[ScrollAlignment](../scrollalignment-class)? alignment\]

)
:::

Scrolls this element into view.

Only one of the alignment options may be specified at a time.

If no options are specified then this will attempt to scroll the minimum
amount needed to bring the element into view.

Note that alignCenter is currently only supported on WebKit platforms.
If alignCenter is specified but not supported then this will fall back
to alignTop.

See also:

-   [scrollIntoView](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollIntoView)
    from MDN.
-   [scrollIntoViewIfNeeded](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollIntoViewIfNeeded)
    from MDN.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void scrollIntoView([ScrollAlignment? alignment]) {
  var hasScrollIntoViewIfNeeded = true;
  hasScrollIntoViewIfNeeded =
      JS('bool', '!!(#.scrollIntoViewIfNeeded)', this);
  if (alignment == ScrollAlignment.TOP) {
    this._scrollIntoView(true);
  } else if (alignment == ScrollAlignment.BOTTOM) {
    this._scrollIntoView(false);
  } else if (hasScrollIntoViewIfNeeded) {
    // TODO(srujzs): This method shouldn't be calling out to
    // `scrollIntoViewIfNeeded`. Remove this and make `scrollIntoView` match
    // the browser definition. If you intend to use `scrollIntoViewIfNeeded`,
    // use the `Element.scrollIntoViewIfNeeded` method.
    if (alignment == ScrollAlignment.CENTER) {
      this.scrollIntoViewIfNeeded(true);
    } else {
      this.scrollIntoViewIfNeeded();
    }
  } else {
    this._scrollIntoView();
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/scrollIntoView.html>
:::

Testing media queries programmatically
======================================

The [DOM](https://developer.mozilla.org/en-US/docs/Glossary/DOM)
provides features that can test the results of a [](css_media_queries.md) programmatically, via the
[`MediaQueryList`](https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryList)
interface and its methods and properties. Once you\'ve created a
`MediaQueryList` object, you can check the result of the query or
receive notifications when the result changes.

Creating a media query list
---------------------------

Before you can evaluate the results of a media query, you need to create
the `MediaQueryList` object representing the query. To do this, use the
[`window.matchMedia`](https://developer.mozilla.org/en-US/docs/Web/API/Window/matchMedia)
method.

For example, to set up a query list that determines if the device is in
landscape or portrait orientation:

[js]

```js
const mediaQueryList = window.matchMedia("(orientation: portrait)");
```

Checking the result of a query
------------------------------

Once you\'ve created your media query list, you can check the result of
the query by looking at the value of its `matches` property:

[js]

```js
if (mediaQueryList.matches) {
  /* The viewport is currently in portrait orientation */
} else {
  /* The viewport is not currently in portrait orientation, therefore landscape */
}
```

Receiving query notifications
-----------------------------

If you need to be aware of changes to the evaluated result of the query
on an ongoing basis, it\'s more efficient to register a
[listener](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)
than to poll the query\'s result. To do this, call the
`addEventListener()` method on the
[`MediaQueryList`](https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryList)
object, with a callback function to invoke when the media query status
changes (e.g., the media query test goes from `true` to `false`):

[js]

```js
// Create the query list.
const mediaQueryList = window.matchMedia("(orientation: portrait)");

// Define a callback function for the event listener.
function handleOrientationChange(mql) {
  // …
}

// Run the orientation change handler once.
handleOrientationChange(mediaQueryList);

// Add the callback function as a listener to the query list.
mediaQueryList.addEventListener("change", handleOrientationChange);
```

This code creates the orientation-testing media query list, then adds an
event listener to it. After defining the listener, we also call the
listener directly. This makes our listener perform adjustments based on
the current device orientation; otherwise, our code might assume the
device is in portrait mode at startup, even if it\'s actually in
landscape mode.

The `handleOrientationChange()` function would look at the result of the
query and handle whatever we need to do on an orientation change:

[js]

```js
function handleOrientationChange(evt) {
  if (evt.matches) {
    /* The viewport is currently in portrait orientation */
  } else {
    /* The viewport is currently in landscape orientation */
  }
}
```

Above, we define the parameter as `evt` --- an event object of type
[`MediaQueryListEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryListEvent)
that also includes the
[`media`](https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryListEvent/media)
and
[`matches`](https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryListEvent/matches)
properties, so you can query these features of the `MediaQueryList` by
directly accessing it, or accessing the event object.

Ending query notifications
--------------------------

To stop receiving notifications about changes to the value of your media
query, call
[`removeEventListener()`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/removeEventListener)
on the `MediaQueryList`, passing it the name of the previously-defined
callback function:

[js]

```js
mediaQueryList.removeEventListener("change", handleOrientationChange);
```

Browser compatibility
---------------------

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`EventTarget_inheritance`

39

16

55

No

26

14

39

39

55

26

14

4.0

`Testing_media_queries`

9

12

6

10

12.1

5.1

≤37

18

6

12.1

5

1.0

`addListener`

9

12

6

10

12.1

5.1

≤37

18

6

12.1

5

1.0

`change_event`

39

79

55

No

26

14

39

39

55

26

14

4.0

`matches`

9

12

6

10

12.1

5.1

≤37

18

6

12.1

5

1.0

`media`

9

12

6

10

12.1

5.1

≤37

18

6

12.1

5

1.0

`removeListener`

9

12

6

10

12.1

5.1

≤37

18

6

12.1

5

1.0

See also
--------

- [Media queries](using_media_queries.md)
- [`window.matchMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/matchMedia)
- [`MediaQueryList`](https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryList)
- [`MediaQueryListEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryListEvent)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries/Testing_media_queries>

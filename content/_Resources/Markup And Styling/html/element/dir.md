\<dir\>: The Directory element
==============================

**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.

The `<dir>` [HTML](../index) element is used as a container for a
directory of files and/or folders, potentially with styles and icons
applied by the [user
agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent). Do
not use this obsolete element; instead, you should use the [`<ul>`](ul)
element for lists, including lists of files.

**Warning:** Do not use this element. Though present in early HTML
specifications, it has been deprecated in HTML 4, and has since been
removed entirely. **No major browsers support this element.**

DOM interface
-------------

This element implements the [`HTMLDirectoryElement`]
interface.

Attributes
----------

Like all other HTML elements, this element supports the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`compact`](#compact) [Deprecated]

:   This Boolean attribute hints that the list should be rendered in a
    compact style. The interpretation of this attribute depends on the
    user agent and it doesn\'t work in all browsers.

Specifications
--------------

Not part of any current specifications.

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

`dir`

1

12

1

≤6

≤12.1

≤4

4.4

18

4

≤12.1

≤3.2

1.0

`compact`

1

12

1

≤6

≤12.1

≤4

4.4

18

4

≤12.1

≤3.2

1.0

See also
--------

- Other list-related HTML Elements: [`<ol>`](ol), [`<ul>`](ul),
    [`<li>`](li), and [`<menu>`](menu);
- CSS properties that may be specially useful to style the `<dir>`
    element:
  - The
        [`list-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style)
        property, useful to choose the way the ordinal is displayed.
  - [CSS
        counters](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_counter_styles/Using_CSS_counters),
        useful to handle complex nested lists.
  - The
        [`line-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height)
        property, useful to simulate the deprecated
        [`compact`](#compact) attribute.
  - The
        [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin)
        property, useful to control the indent of the list.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dir>>

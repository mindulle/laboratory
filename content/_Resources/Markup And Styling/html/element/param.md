\<param\>: The Object Parameter element
=======================================

**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.

The `<param>` [HTML](../index) element defines parameters for an
[`<object>`](object) element.

Attributes
----------

This element includes the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`name`](#name) [Deprecated]

:   Name of the parameter.

[`value`](#value) [Deprecated]

:   Specifies the value of the parameter.

[`type`](#type) [Deprecated]

:   Only used if the `valuetype` is set to `ref`. Specifies the MIME
    type of values found at the URI specified by value.

[`valuetype`](#valuetype) [Deprecated]

:   Specifies the type of the `value` attribute. Possible values are:

    -   `data`: Default value. The value is passed to the object\'s
        implementation as a string.
    -   `ref`: The value is a URI to a resource where run-time values
        are stored.
    -   `object`: An ID of another [`<object>`](object) in the same
        document.

Technical summary
-----------------

  --------------------------------------------- -----------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   None.
  Permitted content                             None; it is a [void element](https://developer.mozilla.org/en-US/docs/Glossary/Void_element).
  Tag omission                                  As it is a void element, the start tag must be present and the end tag must not be present.
  Permitted parents                             An [`<object>`](object) before any [flow content](../content_categories#flow_content).
  Implicit ARIA role                            [No corresponding role](https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role)
  Permitted ARIA roles                          No `role` permitted
  DOM interface                                 [`HTMLParamElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLParamElement)
  --------------------------------------------- -----------------------------------------------------------------------------------------------

Specifications
--------------

  -----------------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-param-element]](https://html.spec.whatwg.org/multipage/obsolete.html#the-param-element)

  -----------------------------------------------------------------------------------------------------

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

`param`

1

12

1

Yes

15

≤4

4.4

18

4

14

≤3.2

1.0

`name`

1

12

1

Yes

15

≤4

4.4

18

4

14

≤3.2

1.0

`type`

1

12

1

Yes

15

≤4

4.4

18

4

14

≤3.2

1.0

`value`

1

12

1

Yes

15

≤4

4.4

18

4

14

≤3.2

1.0

`valuetype`

1

12

1

Yes

15

≤4

4.4

18

4

14

≤3.2

1.0

See also
--------

- [`<object>`](object)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/param>>

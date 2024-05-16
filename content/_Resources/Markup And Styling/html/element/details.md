\<details\>: The Details disclosure element
===========================================

The `<details>` [HTML](../index) element creates a disclosure widget in
which information is visible only when the widget is toggled into an
\"open\" state. A summary or label must be provided using the
[`<summary>`](summary) element.

A disclosure widget is typically presented onscreen using a small
triangle which rotates (or twists) to indicate open/closed status, with
a label next to the triangle. The contents of the `<summary>` element
are used as the label for the disclosure widget.

Try it
------

A `<details>` widget can be in one of two states. The default *closed*
state displays only the triangle and the label inside `<summary>` (or a
[user
agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)-defined
default string if no `<summary>`).

When the user clicks on the widget or focuses it then presses the space
bar, it \"twists\" open, revealing its contents. The common use of a
triangle which rotates or twists around to represent opening or closing
the widget is why these are sometimes called \"twisty\".

You can use CSS to style the disclosure widget, and you can
programmatically open and close the widget by setting/removing its
[`open`](#open) attribute. Unfortunately, at this time, there\'s no
built-in way to animate the transition between open and closed.

By default when closed, the widget is only tall enough to display the
disclosure triangle and summary. When open, it expands to display the
details contained within.

Fully standards-compliant implementations automatically apply the CSS
`display`: list-item to the [`<summary>`](summary) element. You can use
this to customize its appearance further. See [Customizing the
disclosure widget](#customizing_the_disclosure_widget) for further
details.

Attributes
----------

This element includes the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`open`](#open)

:   This Boolean attribute indicates whether the details --- that is,
    the contents of the `<details>` element --- are currently visible.
    The details are shown when this attribute exists, or hidden when
    this attribute is absent. By default this attribute is absent which
    means the details are not visible.

    **Note:** You have to remove this attribute entirely to make the
    details hidden. `open="false"` makes the details visible because
    this attribute is Boolean.

Events
------

In addition to the usual events supported by HTML elements, the
`<details>` element supports the
[`toggle`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDetailsElement/toggle_event)
event, which is dispatched to the `<details>` element whenever its state
changes between open and closed. It is sent *after* the state is
changed, although if the state changes multiple times before the browser
can dispatch the event, the events are coalesced so that only one is
sent.

You can use an event listener for the `toggle` event to detect when the
widget changes state:

[js]

```js
details.addEventListener("toggle", (event) => {
  if (details.open) {
    /* the element was toggled open */
  } else {
    /* the element was toggled closed */
  }
});
```

Examples
--------

### A simple disclosure example

This example shows a simple `<details>` element with a `<summary>`.

[html]

```html
<details>
  <summary>System Requirements</summary>
  <p>
    Requires a computer running an operating system. The computer must have some
    memory and ideally some kind of long-term storage. An input device as well
    as some form of output device is recommended.
  </p>
</details>
```

#### Result

### Creating an open disclosure box

To start the `<details>` box in its open state, add the Boolean `open`
attribute:

[html]

```html
<details open>
  <summary>System Requirements</summary>
  <p>
    Requires a computer running an operating system. The computer must have some
    memory and ideally some kind of long-term storage. An input device as well
    as some form of output device is recommended.
  </p>
</details>
```

#### Result

### Customizing the appearance

Now let\'s apply some CSS to customize the appearance of the disclosure
box.

#### CSS

[css]

```css
details {
  font:
    16px "Open Sans",
    Calibri,
    sans-serif;
  width: 620px;
}

details > summary {
  padding: 2px 6px;
  width: 15em;
  background-color: #ddd;
  border: none;
  box-shadow: 3px 3px 4px black;
  cursor: pointer;
}

details > p {
  border-radius: 0 0 10px 10px;
  background-color: #ddd;
  padding: 2px 6px;
  margin: 0;
  box-shadow: 3px 3px 4px black;
}

details[open] > summary {
  background-color: #ccf;
}

```

This CSS creates a look similar to a tabbed interface, where clicking
the tab opens it to reveal its contents.

The selector `details[open]` can be used to style the element which is
open.

#### HTML

[html]

```html
<details>
  <summary>System Requirements</summary>
  <p>
    Requires a computer running an operating system. The computer must have some
    memory and ideally some kind of long-term storage. An input device as well
    as some form of output device is recommended.
  </p>
</details>
```

#### Result

### Customizing the disclosure widget

The disclosure triangle itself can be customized, although this is not
as broadly supported. There are variations in how browsers support this
customization due to experimental implementations as the element was
standardized, so we\'ll have to use multiple approaches for a while.

The [`<summary>`](summary) element supports the
[`list-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style)
shorthand property and its longhand properties, such as
[`list-style-type`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type),
to change the disclosure triangle to whatever you choose (usually with
[`list-style-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-image)).
For example, we can remove the disclosure widget icon by setting
`list-style: none`.

#### CSS

[css]

```css
details {
  font:
    16px "Open Sans",
    Calibri,
    sans-serif;
  width: 620px;
}

details > summary {
  padding: 2px 6px;
  width: 15em;
  background-color: #ddd;
  border: none;
  box-shadow: 3px 3px 4px black;
  cursor: pointer;
  list-style: none;
}

details > p {
  border-radius: 0 0 10px 10px;
  background-color: #ddd;
  padding: 2px 6px;
  margin: 0;
  box-shadow: 3px 3px 4px black;
}

```

This CSS creates a look similar to a tabbed interface, where activating
the tab expands and opens it to reveal its contents.

#### HTML

[html]

```html
<details>
  <summary>System Requirements</summary>
  <p>
    Requires a computer running an operating system. The computer must have some
    memory and ideally some kind of long-term storage. An input device as well
    as some form of output device is recommended.
  </p>
</details>
```

#### Result

Technical summary
-----------------

  --------------------------------------------- -------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), sectioning root, interactive content, palpable content.
  Permitted content                             One [`<summary>`](summary) element followed by [flow content](../content_categories#flow_content).
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [flow content](../content_categories#flow_content).
  Implicit ARIA role                            [`group`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/group_role)
  Permitted ARIA roles                          No `role` permitted
  DOM interface                                 [`HTMLDetailsElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDetailsElement)
  --------------------------------------------- -------------------------------------------------------------------------------------------------------------

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-details-element]](https://html.spec.whatwg.org/multipage/interactive-elements.html#the-details-element)

  ---------------------------------------------------------------------------------------------------------------------

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

`details`

12

79

49Before Firefox 57, there was a bug meaning that `<details>` elements
can\'t be made open by default using the `open` attribute if they have a
CSS `animation` active on them.

No

15

6

4.4

18

49There is a bug meaning that `<details>` elements can\'t be made open
by default using the `open` attribute if they have a CSS `animation`
active on them.

14

6

1.0

`name`

120

120

No

No

No

No

No

No

No

No

No

No

`open`

12

79

49

No

15

6

4.4

18

49

14

6

1.0

See also
--------

- [`<summary>`](summary)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details>>

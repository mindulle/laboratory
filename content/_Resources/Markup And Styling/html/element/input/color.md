\<input type=\"color\"\>
========================

[`<input>`](../input) elements of type `color` provide a user interface
element that lets a user specify a color, either by using a visual color
picker interface or by entering the color into a text field in `#rrggbb`
hexadecimal format.

Only simple colors (without alpha channel) are allowed though CSS colors
has more formats, e.g. color names, functional notations and a
hexadecimal format with an alpha channel.

The element\'s presentation may vary substantially from one browser
and/or platform to another---it might be a simple textual input that
automatically validates to ensure that the color information is entered
in the proper format, or a platform-standard color picker, or some kind
of custom color picker window.

Try it
------

Value
-----

The [`value`](../input#value) of an [`<input>`](../input) element of
type `color` is always a string which contains a 7-character string
specifying an RGB color in hexadecimal format. While you can input the
color in either upper- or lower-case, it will be stored in lower-case
form. The value is never in any other form, and is never empty.

**Note:** Setting the value to anything that isn\'t a valid,
fully-opaque, RGB color *in hexadecimal notation* will result in the
value being set to `#000000`. In particular, you can\'t use CSS\'s
standardized color names, or any CSS function syntax, to set the value.
This makes sense when you keep in mind that HTML and CSS are separate
languages and specifications. In addition, colors with an alpha channel
are not supported; specifying a color in 9-character hexadecimal
notation (e.g. `#009900aa`) will also result in the color being set to
`#000000`.

Using color inputs
------------------

Inputs of type `color` are simple, due to the limited number of
attributes they support.

### Providing a default color

You can update the simple example above to set a default value, so that
the color picker is pre-filled with the default color and the color
picker (if any) will also default to that color:

[html]

```html
<input type="color" value="#ff0000" />
```

If you don\'t specify a value, the default is `#000000`, which is black.
The value must be in seven-character hexadecimal notation, meaning the
\"\#\" character followed by two digits each representing red, green,
and blue, like this: `#rrggbb`. If you have colors that are in any other
format (such as CSS color names or CSS color functions such as `rgb()`
or `rgba()`), you\'ll have to convert them to hexadecimal before setting
the `value`.

### Tracking color changes

As is the case with other [`<input>`](../input) types, there are two
events that can be used to detect changes to the color value:
[`input`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/input_event)
and
[`change`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/change_event).
`input` is fired on the `<input>` element every time the color changes.
The `change` event is fired when the user dismisses the color picker. In
both cases, you can determine the new value of the element by looking at
its [`value`](../input#value).

Here\'s an example that watches changes over time to the color value:

[js]

```js
colorPicker.addEventListener("input", updateFirst, false);
colorPicker.addEventListener("change", watchColorPicker, false);

function watchColorPicker(event) {
  document.querySelectorAll("p").forEach((p) => {
    p.style.color = event.target.value;
  });
}
```

### Selecting the value

When a browser doesn\'t support a color picker interface, its
implementation of color inputs will be a text box that validates the
contents automatically to ensure that the value is in the correct
format. In this case you can use the
[`select()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/select)
method to select the text currently in the edit field.

If the browser instead uses a color picker, `select()` does nothing. You
should be aware of this behavior so your code can respond appropriately
in either case.

[js]

```js
colorPicker.select();
```

Validation
----------

A color input\'s value is considered to be invalid if the [user
agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) is
unable to convert the user\'s input into seven-character lower-case
hexadecimal notation. If and when this is the case, the
[`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid)
pseudo-class is applied to the element.

Example
-------

Let\'s create an example which does a little more with the color input
by tracking the
[`change`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/change_event)
and
[`input`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/input_event)
events to take the new color and apply it to every [`<p>`](../p) element
in the document.

### HTML

The HTML is fairly straightforward --- a couple of paragraphs of
descriptive material with an [`<input>`](../input) of type `color` with
the ID `color-picker`, which we\'ll use to change the color of the
paragraphs\' text.

[html]

```html
<p>
  An example demonstrating the use of the
  <code>&lt;input type="color"&gt;</code> control.
</p>

<label for="color-picker">Color:</label>
<input type="color" value="#ff0000" id="color-picker" />

<p>
  Watch the paragraph colors change when you adjust the color picker. As you
  make changes in the color picker, the first paragraph's color changes, as a
  preview (this uses the <code>input</code> event). When you close the color
  picker, the <code>change</code> event fires, and we detect that to change
  every paragraph to the selected color.
</p>
```

### JavaScript

First, there\'s some setup. Here we establish some variables, setting up
a variable that contains the color we\'ll set the color picker to when
we first load up, and then setting up a
[`load`](https://developer.mozilla.org/en-US/docs/Web/API/Window/load_event)
handler to do the main startup work once the page is fully loaded.

[js]

```js
let colorPicker;
const defaultColor = "#0000ff";

window.addEventListener("load", startup, false);
```

#### Initialization

Once the page is loaded, our `load` event handler, `startup()`, is
called:

[js]

```js
function startup() {
  colorPicker = document.querySelector("#color-picker");
  colorPicker.value = defaultColor;
  colorPicker.addEventListener("input", updateFirst, false);
  colorPicker.addEventListener("change", updateAll, false);
  colorPicker.select();
}
```

This gets a reference to the color `<input>` element in a variable
called `colorPicker`, then sets the color input\'s value to the value in
`defaultColor`. Then the color input\'s
[`input`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/input_event)
event is set up to call our `updateFirst()` function, and the
[`change`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/change_event)
event is set to call `updateAll()`. These are both seen below.

Finally, we call
[`select()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/select)
to select the text content of the color input if the control is
implemented as a text field (this has no effect if a color picker
interface is provided instead).

#### Reacting to color changes

We provide two functions that deal with color changes. The
`updateFirst()` function is called in response to the `input` event. It
changes the color of the first paragraph element in the document to
match the new value of the color input. Since `input` events are fired
every time an adjustment is made to the value (for example, if the
brightness of the color is increased), these will happen repeatedly as
the color picker is used.

[js]

```js
function updateFirst(event) {
  const p = document.querySelector("p");
  if (p) {
    p.style.color = event.target.value;
  }
}
```

When the color picker is dismissed, indicating that the value will not
change again (unless the user re-opens the color picker), a `change`
event is sent to the element. We handle that event using the
`updateAll()` function, using [`Event.target.value`](../input#value) to
obtain the final selected color:

[js]

```js
function updateAll(event) {
  document.querySelectorAll("p").forEach((p) => {
    p.style.color = event.target.value;
  });
}
```

This sets the color of every [`<p>`](../p) block so that its
[`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color)
attribute matches the current value of the color input, which is
referred to using
[`event.target`](https://developer.mozilla.org/en-US/docs/Web/API/Event/target).

### Result

The final result looks like this:

Technical summary
-----------------

  --------------------------------- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  **[Value](#value)**               A 7-character string specifying a [`<color>`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value) in lower-case hexadecimal notation
  **Events**                        [`change`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/change_event) and [`input`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/input_event)
  **Supported common attributes**   [`autocomplete`](../input#autocomplete) and [`list`](../input#list)
  **IDL attributes**                `list` and `value`
  **DOM interface**                 [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)
  **Methods**                       [`select()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/select)
  **Implicit ARIA Role**            [`no corresponding role`](https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role)
  --------------------------------- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  ----------------------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  color-state-(type=color)]](https://html.spec.whatwg.org/multipage/input.html#color-state-(type=color))

  ----------------------------------------------------------------------------------------------------------------

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

`color`

20

14

29

No

12

12.1

4.4

25

27Firefox for Android doesn\'t allow the user to choose a custom color,
only one of the predefined ones.

12

12.2

1.5

`autocomplete`

20

14

No

No

15

No

4.4

25

No

14

No

1.5

`list`

20

14

110The `list` attribute is supported in Firefox for Windows and Linux.
See [bug 960984](https://bugzil.la/960984).

No

15

12.1

4.4

25

No

14

12.2

1.5

See also
--------

- [Compatibility of CSS
    properties](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/color>>

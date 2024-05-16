\<input type=\"button\"\>
=========================

[`<input>`](../input) elements of type `button` are rendered as simple
push buttons, which can be programmed to control custom functionality
anywhere on a webpage as required when assigned an event handler
function (typically for the
[`click`](https://developer.mozilla.org/en-US/docs/Web/API/Element/click_event)
event).

Try it
------

**Note:** While `<input>` elements of type `button` are still perfectly
valid HTML, the newer [`<button>`](../button) element is now the favored
way to create buttons. Given that a [`<button>`](../button)\'s label
text is inserted between the opening and closing tags, you can include
HTML in the label, even images.

Value
-----

### Button with a value

An `<input type="button">` elements\' [`value`](../input#value)
attribute contains a string that is used as the button\'s label.

[html]

```html
<input type="button" value="Click Me" />
```

### Button without a value

If you don\'t specify a `value`, you get an empty button:

[html]

```html
<input type="button" />
```

Using buttons
-------------

`<input type="button">` elements have no default behavior (their
cousins, `<input type="submit">` and [`<input type="reset">`](reset) are
used to submit and reset forms, respectively). To make buttons do
anything, you have to write JavaScript code to do the work.

### A simple button

We\'ll begin by creating a simple button with a
[`click`](https://developer.mozilla.org/en-US/docs/Web/API/Element/click_event)
event handler that starts our machine (well, it toggles the `value` of
the button and the text content of the following paragraph):

[html]

```html
<form>
  <input type="button" value="Start machine" />
</form>
<p>The machine is stopped.</p>
```

[js]

```js
const button = document.querySelector("input");
const paragraph = document.querySelector("p");

button.addEventListener("click", updateButton);

function updateButton() {
  if (button.value === "Start machine") {
    button.value = "Stop machine";
    paragraph.textContent = "The machine has started!";
  } else {
    button.value = "Start machine";
    paragraph.textContent = "The machine is stopped.";
  }
}
```

The script gets a reference to the
[`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)
object representing the `<input>` in the DOM, saving this reference in
the variable `button`.
[`addEventListener()`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)
is then used to establish a function that will be run when
[`click`](https://developer.mozilla.org/en-US/docs/Web/API/Element/click_event)
events occur on the button.

### Adding keyboard shortcuts to buttons

Keyboard shortcuts, also known as access keys and keyboard equivalents,
let the user trigger a button using a key or combination of keys on the
keyboard. To add a keyboard shortcut to a button --- just as you would
with any [`<input>`](../input) for which it makes sense --- you use the
[`accesskey`](../../global_attributes/accesskey) global attribute.

In this example, [s] is specified as the access key (you\'ll need
to press [s] plus the particular modifier keys for your browser/OS
combination; see [accesskey](../../global_attributes/accesskey) for a
useful list of those).

[html]

```html
<form>
  <input type="button" value="Start machine" accesskey="s" />
</form>
<p>The machine is stopped.</p>
```

**Note:** The problem with the above example of course is that the user
will not know what the access key is! In a real site, you\'d have to
provide this information in a way that doesn\'t interfere with the site
design (for example by providing an easily accessible link that points
to information on what the site accesskeys are).

### Disabling and enabling a button

To disable a button, specify the [`disabled`](../../attributes/disabled)
global attribute on it, like so:

[html]

```html
<input type="button" value="Disable me" disabled />
```

#### Setting the disabled attribute

You can enable and disable buttons at run time by setting `disabled` to
`true` or `false`. In this example our button starts off enabled, but if
you press it, it is disabled using `button.disabled = true`. A
[`setTimeout()`](https://developer.mozilla.org/en-US/docs/Web/API/setTimeout)
function is then used to reset the button back to its enabled state
after two seconds.

[html]

```html
<input type="button" value="Enabled" />
```

[js]

```js
const button = document.querySelector("input");

button.addEventListener("click", disableButton);

function disableButton() {
  button.disabled = true;
  button.value = "Disabled";
  setTimeout(() => {
    button.disabled = false;
    button.value = "Enabled";
  }, 2000);
}
```

#### Inheriting the disabled state

If the `disabled` attribute isn\'t specified, the button inherits its
`disabled` state from its parent element. This makes it possible to
enable and disable groups of elements all at once by enclosing them in a
container such as a [`<fieldset>`](../fieldset) element, and then
setting `disabled` on the container.

The example below shows this in action. This is very similar to the
previous example, except that the `disabled` attribute is set on the
`<fieldset>` when the first button is pressed --- this causes all three
buttons to be disabled until the two second timeout has passed.

[html]

```html
<fieldset>
  <legend>Button group</legend>
  <input type="button" value="Button 1" />
  <input type="button" value="Button 2" />
  <input type="button" value="Button 3" />
</fieldset>
```

[js]

```js
const button = document.querySelector("input");
const fieldset = document.querySelector("fieldset");

button.addEventListener("click", disableButton);

function disableButton() {
  fieldset.disabled = true;
  setTimeout(() => {
    fieldset.disabled = false;
  }, 2000);
}
```

**Note:** Firefox will, unlike other browsers, by default, [persist the
dynamic disabled
state](https://stackoverflow.com/questions/5985839/bug-with-firefox-disabled-attribute-of-input-not-resetting-when-refreshing)
of a [`<button>`](../button) across page loads. Use the
[`autocomplete`](../button#autocomplete) attribute to control this
feature.

Validation
----------

Buttons don\'t participate in constraint validation; they have no real
value to be constrained.

Examples
--------

The below example shows a very simple drawing app created using a
[`<canvas>`](../canvas) element and some simple CSS and JavaScript
(we\'ll hide the CSS for brevity). The top two controls allow you to
choose the color and size of the drawing pen. The button, when clicked,
invokes a function that clears the canvas.

[html]

```html
<div class="toolbar">
  <input type="color" aria-label="select pen color" />
  <input
    type="range"
    min="2"
    max="50"
    value="30"
    aria-label="select pen size" /><span class="output">30</span>
  <input type="button" value="Clear canvas" />
</div>

<canvas class="myCanvas">
  <p>Add suitable fallback here.</p>
</canvas>
```

[js]

```js
const canvas = document.querySelector(".myCanvas");
const width = (canvas.width = window.innerWidth);
const height = (canvas.height = window.innerHeight - 85);
const ctx = canvas.getContext("2d");

ctx.fillStyle = "rgb(0,0,0)";
ctx.fillRect(0, 0, width, height);

const colorPicker = document.querySelector('input[type="color"]');
const sizePicker = document.querySelector('input[type="range"]');
const output = document.querySelector(".output");
const clearBtn = document.querySelector('input[type="button"]');

// covert degrees to radians
function degToRad(degrees) {
  return (degrees * Math.PI) / 180;
}

// update sizepicker output value

sizePicker.oninput = () => {
  output.textContent = sizePicker.value;
};

// store mouse pointer coordinates, and whether the button is pressed
let curX;
let curY;
let pressed = false;

// update mouse pointer coordinates
document.onmousemove = (e) => {
  curX = e.pageX;
  curY = e.pageY;
};

canvas.onmousedown = () => {
  pressed = true;
};

canvas.onmouseup = () => {
  pressed = false;
};

clearBtn.onclick = () => {
  ctx.fillStyle = "rgb(0,0,0)";
  ctx.fillRect(0, 0, width, height);
};

function draw() {
  if (pressed) {
    ctx.fillStyle = colorPicker.value;
    ctx.beginPath();
    ctx.arc(
      curX,
      curY - 85,
      sizePicker.value,
      degToRad(0),
      degToRad(360),
      false,
    );
    ctx.fill();
  }

  requestAnimationFrame(draw);
}

draw();
```

Technical summary
-----------------

  --------------------------------- -----------------------------------------------------------------------------------------------
  **[Value](#value)**               A string used as the button\'s label
  **Events**                        [`click`](https://developer.mozilla.org/en-US/docs/Web/API/Element/click_event)
  **Supported common attributes**   [`type`](../input#type) and [`value`](../input#value)
  **IDL attributes**                `value`
  **DOM interface**                 [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)
  **Methods**                       None
  **Implicit ARIA Role**            [`button`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/button_role)
  --------------------------------- -----------------------------------------------------------------------------------------------

Specifications
--------------

  --------------------------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  button-state-(type=button)]](https://html.spec.whatwg.org/multipage/input.html#button-state-(type=button))

  --------------------------------------------------------------------------------------------------------------------

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

`button`

1

12

1

Yes

15

1

4.4

18

4

14

1

1.0

See also
--------

- [`<input>`](../input) and the
    [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement)
    interface which implements it.
- The more modern [`<button>`](../button) element.
- [Compatibility of CSS
    properties](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/button>>

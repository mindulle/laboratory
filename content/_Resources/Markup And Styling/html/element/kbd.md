\<kbd\>: The Keyboard Input element
===================================

The `<kbd>` [HTML](../index) element represents a span of inline text
denoting textual user input from a keyboard, voice input, or any other
text entry device. By convention, the [user
agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)
defaults to rendering the contents of a `<kbd>` element using its
default monospace font, although this is not mandated by the HTML
standard.

Try it
------

`<kbd>` may be nested in various combinations with the [`<samp>`](samp)
(Sample Output) element to represent various forms of input or output
based on visual cues.

Attributes
----------

This element only includes the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

Usage notes
-----------

Other elements can be used in tandem with `<kbd>` to represent more
specific scenarios:

- Nesting a `<kbd>` element within another `<kbd>` element represents
    an actual key or other unit of input as a portion of a larger input.
    See [Representing keystrokes within an
    input](#representing_keystrokes_within_an_input) below.
- Nesting a `<kbd>` element inside a [`<samp>`](samp) element
    represents input that has been echoed back to the user by the
    system. See [Echoed input](#echoed_input), below, for an example.
- Nesting a `<samp>` element inside a `<kbd>` element, on the other
    hand, represents input which is based on text presented by the
    system, such as the names of menus and menu items, or the names of
    buttons displayed on the screen. See the example under [Representing
    onscreen input options](#representing_onscreen_input_options) below.

**Note:** You can define a custom style to override the browser\'s
default font selection for the `<kbd>` element, although the user\'s
preferences may potentially override your CSS.

Examples
--------

### Basic example

[html]

```html
<p>
  Use the command <kbd>help mycommand</kbd> to view documentation for the
  command "mycommand".
</p>
```

#### Result

### Representing keystrokes within an input

To describe an input comprised of multiple keystrokes, you can nest
multiple `<kbd>` elements, with an outer `<kbd>` element representing
the overall input and each individual keystroke or component of the
input enclosed within its own `<kbd>`.

#### Unstyled

First, let\'s look at what this looks like as just plain HTML.

##### HTML

[html]

```html
<p>
  You can also create a new document using the
  <kbd><kbd>Ctrl</kbd>+<kbd>N</kbd></kbd> keyboard shortcut.
</p>
```

This wraps the entire key sequence in an outer `<kbd>` element, then
each individual key within its own, in order to denote the components of
the sequence.

**Note:** You don\'t need to do all this wrapping; you can choose to
simplify it by leaving out the external `<kbd>` element. In other words,
simplifying this to just `<kbd>Ctrl</kbd>+<kbd>N</kbd>` would be
perfectly valid.

**Note:** Depending on your style sheet, though, you may find it useful
to do this kind of nesting.

##### Result

The output looks like this without a style sheet applied:

#### With custom styles

We can make more sense of this by adding some CSS:

##### CSS

We add a new selector for nested `<kbd>` elements, `kbd>kbd`, which we
can apply when rendering keyboard keys:

[css]

```css
kbd > kbd {
  border-radius: 3px;
  padding: 1px 2px 0;
  border: 1px solid black;
}

```

##### HTML

Then we update the HTML to use this class on the keys in the output to
be presented:

[html]

```html
<p>
  You can also create a new document by pressing the
  <kbd><kbd>Ctrl</kbd>+<kbd>N</kbd></kbd> shortcut.
</p>
```

##### Result

The result is just what we want!

### Echoed input

Nesting a `<kbd>` element inside a [`<samp>`](samp) element represents
input that has been echoed back to the user by the system.

[html]

```html
<p>
  If a syntax error occurs, the tool will output the initial command you typed
  for your review:
</p>
<blockquote>
  <samp><kbd>custom-git ad my-new-file.cpp</kbd></samp>
</blockquote>
```

#### Result

### Representing onscreen input options

Nesting a `<samp>` element inside a `<kbd>` element represents input
which is based on text presented by the system, such as the names of
menus and menu items, or the names of buttons displayed on the screen.

For example, you can explain how to choose the \"New Document\" option
in the \"File\" menu using HTML that looks like this:

[html]

```html
<p>
  To create a new file, choose the <kbd><kbd><samp>File</samp></kbd>
  ⇒<kbd><samp>New Document</samp></kbd></kbd> menu option.
</p>

<p>
  Don't forget to click the <kbd><samp>OK</samp></kbd> button to confirm once
  you've entered the name of the new file.
</p>
```

This does some interesting nesting. For the menu option description, the
entire input is enclosed in a `<kbd>` element. Then, inside that, both
the menu and menu item names are contained within both `<kbd>` and
`<samp>`, indicating an input which is selected from a screen widget.

#### Result

Technical summary
-----------------

  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [phrasing content](../content_categories#phrasing_content), palpable content.
  Permitted content                             [Phrasing content](../content_categories#phrasing_content).
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [phrasing content](../content_categories#phrasing_content).
  Implicit ARIA role                            [No corresponding role](https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role)
  Permitted ARIA roles                          Any
  DOM interface                                 [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  -------------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-kbd-element]](https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-kbd-element)

  -------------------------------------------------------------------------------------------------------------

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

`kbd`

1

12

1Before Firefox 4, creating a \<kbd\> element incorrectly resulted in an
`HTMLSpanElement` object, instead of the expected `HTMLElement`.

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

- [`<code>`](code)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/kbd>>

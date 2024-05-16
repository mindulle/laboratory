Global attributes
=================

**Global attributes** are attributes common to all HTML elements; they
can be used on all elements, though they may have no effect on some
elements.

Global attributes may be specified on all [HTML elements](_Resources/Markup%20And%20Styling/html/element/index.md),
*even those not specified in the standard*. That means that any
non-standard elements must still permit these attributes, even though
using those elements means that the document is no longer
HTML5-compliant. For example, HTML5-compliant browsers hide content
marked as `<foo hidden>…</foo>`, even though `<foo>` is not a valid HTML
element.

In addition to the basic HTML global attributes, the following global
attributes also exist:

- `xml:lang` and `xml:base` --- these are inherited from the XHTML
    specifications and deprecated, but kept for compatibility purposes.
- The ARIA
    [`role`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles)
    attribute and the multiple
    [`aria-*`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes)
    states and properties, used for ensuring accessibility.
- The [event handler](_Resources/Markup%20And%20Styling/html/attributes/index.md#event_handler_attributes) attributes:
    `onabort`, `onautocomplete`, `onautocompleteerror`, `onblur`,
    `oncancel`, `oncanplay`, `oncanplaythrough`, `onchange`, `onclick`,
    `onclose`, `oncontextmenu`, `oncuechange`, `ondblclick`, `ondrag`,
    `ondragend`, `ondragenter`, `ondragleave`, `ondragover`,
    `ondragstart`, `ondrop`, `ondurationchange`, `onemptied`, `onended`,
    `onerror`, `onfocus`, `oninput`, `oninvalid`, `onkeydown`,
    `onkeypress`, `onkeyup`, `onload`, `onloadeddata`,
    `onloadedmetadata`, `onloadstart`, `onmousedown`, `onmouseenter`,
    `onmouseleave`, `onmousemove`, `onmouseout`, `onmouseover`,
    `onmouseup`, `onmousewheel`, `onpause`, `onplay`, `onplaying`,
    `onprogress`, `onratechange`, `onreset`, `onresize`, `onscroll`,
    `onseeked`, `onseeking`, `onselect`, `onshow`, `onsort`,
    `onstalled`, `onsubmit`, `onsuspend`, `ontimeupdate`, `ontoggle`,
    `onvolumechange`, `onwaiting`.

List of global attributes
-------------------------

[`accesskey`](global_attributes/accesskey)

:   Provides a hint for generating a keyboard shortcut for the current
    element. This attribute consists of a space-separated list of
    characters. The browser should use the first one that exists on the
    computer keyboard layout.

[`autocapitalize`](global_attributes/autocapitalize)

:   Controls whether and how text input is automatically capitalized as
    it is entered/edited by the user. It can have the following values:

    -   `off` or `none`, no autocapitalization is applied (all letters
        default to lowercase)
    -   `on` or `sentences`, the first letter of each sentence defaults
        to a capital letter; all other letters default to lowercase
    -   `words`, the first letter of each word defaults to a capital
        letter; all other letters default to lowercase
    -   `characters`, all letters should default to uppercase

[`autofocus`](global_attributes/autofocus)

:   Indicates that an element is to be focused on page load, or as soon
    as the [`<dialog>`](element/dialog) it is part of is displayed. This
    attribute is a boolean, initially false.

[`class`](global_attributes/class)

:   A space-separated list of the classes of the element. Classes allow
    CSS and JavaScript to select and access specific elements via the
    [class
    selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Class_selectors)
    or functions like the method
    [`Document.getElementsByClassName()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByClassName).

[`contenteditable`](global_attributes/contenteditable)

:   An
    [enumerated](https://developer.mozilla.org/en-US/docs/Glossary/Enumerated)
    attribute indicating if the element should be editable by the user.
    If so, the browser modifies its widget to allow editing. The
    attribute must take one of the following values:

    -   `true` or the *empty string*, which indicates that the element
        must be editable;
    -   `false`, which indicates that the element must not be editable.

[`contextmenu`](global_attributes/contextmenu) [Deprecated]

:   The [`id`](#id) of a [`<menu>`](element/menu) to use as the
    contextual menu for this element.

[`data-*`](global_attributes/data-*)

:   Forms a class of attributes, called custom data attributes, that
    allow proprietary information to be exchanged between the
    [HTML](index) and its
    [DOM](https://developer.mozilla.org/en-US/docs/Glossary/DOM)
    representation that may be used by scripts. All such custom data are
    available via the
    [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
    interface of the element the attribute is set on. The
    [`HTMLElement.dataset`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/dataset)
    property gives access to them.

[`dir`](global_attributes/dir)

:   An enumerated attribute indicating the directionality of the
    element\'s text. It can have the following values:

    -   `ltr`, which means *left to right* and is to be used for
        languages that are written from the left to the right (like
        English);
    -   `rtl`, which means *right to left* and is to be used for
        languages that are written from the right to the left (like
        Arabic);
    -   `auto`, which lets the user agent decide. It uses a basic
        algorithm as it parses the characters inside the element until
        it finds a character with a strong directionality, then it
        applies that directionality to the whole element.

[`draggable`](global_attributes/draggable)

:   An enumerated attribute indicating whether the element can be
    dragged, using the [Drag and Drop
    API](https://developer.mozilla.org/en-US/docs/Web/API/HTML_Drag_and_Drop_API).
    It can have the following values:

    -   `true`, which indicates that the element may be dragged
    -   `false`, which indicates that the element may not be dragged.

[`enterkeyhint`](global_attributes/enterkeyhint)

:   Hints what action label (or icon) to present for the enter key on
    virtual keyboards.

[`exportparts`](global_attributes/exportparts) [Experimental]

:   Used to transitively export shadow parts from a nested shadow tree
    into a containing light tree.

[`hidden`](global_attributes/hidden)

:   An enumerated attribute indicating that the element is not yet, or
    is no longer, *relevant*. For example, it can be used to hide
    elements of the page that can\'t be used until the login process has
    been completed. The browser won\'t render such elements. This
    attribute must not be used to hide content that could legitimately
    be shown.

[`id`](global_attributes/id)

:   Defines a unique identifier (ID) which must be unique in the whole
    document. Its purpose is to identify the element when linking (using
    a fragment identifier), scripting, or styling (with CSS).

[`inert`](global_attributes/inert)

:   A boolean value that makes the browser disregard user input events
    for the element. Useful when click events are present.

[`inputmode`](global_attributes/inputmode)

:   Provides a hint to browsers about the type of virtual keyboard
    configuration to use when editing this element or its contents. Used
    primarily on [`<input>`](element/input) elements, but is usable on
    any element while in [`contenteditable`](#contenteditable) mode.

[`is`](global_attributes/is)

:   Allows you to specify that a standard HTML element should behave
    like a registered custom built-in element (see [Using custom
    elements](https://developer.mozilla.org/en-US/docs/Web/API/Web_components/Using_custom_elements)
    for more details).

**Note:** The `item*` attributes are part of the [WHATWG HTML Microdata
feature](https://html.spec.whatwg.org/multipage/microdata.html#microdata).

[`itemid`](global_attributes/itemid)

:   The unique, global identifier of an item.

[`itemprop`](global_attributes/itemprop)

:   Used to add properties to an item. Every HTML element may have an
    `itemprop` attribute specified, where an `itemprop` consists of a
    name and value pair.

[`itemref`](global_attributes/itemref)

:   Properties that are not descendants of an element with the
    `itemscope` attribute can be associated with the item using an
    `itemref`. It provides a list of element ids (not `itemid`s) with
    additional properties elsewhere in the document.

[`itemscope`](global_attributes/itemscope)

:   `itemscope` (usually) works along with
    [`itemtype`](global_attributes/itemtype) to specify that the HTML
    contained in a block is about a particular item. `itemscope` creates
    the Item and defines the scope of the `itemtype` associated with it.
    `itemtype` is a valid URL of a vocabulary (such as
    [schema.org](https://schema.org/)) that describes the item and its
    properties context.

[`itemtype`](global_attributes/itemtype)

:   Specifies the URL of the vocabulary that will be used to define
    `itemprop`s (item properties) in the data structure.
    [`itemscope`](global_attributes/itemscope) is used to set the scope
    of where in the data structure the vocabulary set by `itemtype` will
    be active.

[`lang`](global_attributes/lang)

:   Helps define the language of an element: the language that
    non-editable elements are in, or the language that editable elements
    should be written in by the user. The attribute contains one
    \"language tag\" (made of hyphen-separated \"language subtags\") in
    the format defined in [RFC 5646: Tags for Identifying Languages
    (also known as
    BCP 47)](https://datatracker.ietf.org/doc/html/rfc5646). `xml:lang`
    has priority over it.

[`nonce`](global_attributes/nonce)

:   A cryptographic nonce (\"number used once\") which can be used by
    [Content Security
    Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP) to
    determine whether or not a given fetch will be allowed to proceed.

[`part`](global_attributes/part)

:   A space-separated list of the part names of the element. Part names
    allows CSS to select and style specific elements in a shadow tree
    via the
    [`::part`](https://developer.mozilla.org/en-US/docs/Web/CSS/::part)
    pseudo-element.

[`popover`](global_attributes/popover)

:   Used to designate an element as a popover element (see [Popover
    API](https://developer.mozilla.org/en-US/docs/Web/API/Popover_API)).
    Popover elements are hidden via `display: none` until opened via an
    invoking/control element (i.e. a `<button>` or
    `<input type="button">` with a
    [`popovertarget`](element/button#popovertarget) attribute) or a
    [`HTMLElement.showPopover()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/showPopover)
    call.

[`role`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles)

:   Roles define the semantic meaning of content, allowing screen
    readers and other tools to present and support interaction with an
    object in a way that is consistent with user expectations of that
    type of object. `roles` are added to HTML elements using
    `role="role_type"`, where `role_type` is the name of a role in the
    ARIA specification.

[`slot`](global_attributes/slot)

:   Assigns a slot in a [shadow
    DOM](https://developer.mozilla.org/en-US/docs/Web/API/Web_components/Using_shadow_DOM)
    shadow tree to an element: An element with a `slot` attribute is
    assigned to the slot created by the [`<slot>`](element/slot) element
    whose [`name`](element/slot#name) attribute\'s value matches that
    `slot` attribute\'s value.

[`spellcheck`](global_attributes/spellcheck)

:   An enumerated attribute defines whether the element may be checked
    for spelling errors. It may have the following values:

    -   empty string or `true`, which indicates that the element should
        be, if possible, checked for spelling errors;
    -   `false`, which indicates that the element should not be checked
        for spelling errors.

[`style`](global_attributes/style)

:   Contains [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
    styling declarations to be applied to the element. Note that it is
    recommended for styles to be defined in a separate file or files.
    This attribute and the [`<style>`](element/style) element have
    mainly the purpose of allowing for quick styling, for example for
    testing purposes.

[`tabindex`](global_attributes/tabindex)

:   An integer attribute indicating if the element can take input focus
    (is *focusable*), if it should participate to sequential keyboard
    navigation, and if so, at what position. It can take several values:

    -   a *negative value* means that the element should be focusable,
        but should not be reachable via sequential keyboard navigation;
    -   `0` means that the element should be focusable and reachable via
        sequential keyboard navigation, but its relative order is
        defined by the platform convention;
    -   a *positive value* means that the element should be focusable
        and reachable via sequential keyboard navigation; the order in
        which the elements are focused is the increasing value of the
        [**tabindex**](#tabindex). If several elements share the same
        tabindex, their relative order follows their relative positions
        in the document.

[`title`](global_attributes/title)

:   Contains a text representing advisory information related to the
    element it belongs to. Such information can typically, but not
    necessarily, be presented to the user as a tooltip.

[`translate`](global_attributes/translate)

:   An enumerated attribute that is used to specify whether an
    element\'s attribute values and the values of its
    [`Text`](https://developer.mozilla.org/en-US/docs/Web/API/Text) node
    children are to be translated when the page is localized, or whether
    to leave them unchanged. It can have the following values:

    -   empty string or `yes`, which indicates that the element will be
        translated.
    -   `no`, which indicates that the element will not be translated.

[`virtualkeyboardpolicy`](global_attributes/virtualkeyboardpolicy)

:   An
    [enumerated](https://developer.mozilla.org/en-US/docs/Glossary/Enumerated)
    attribute used to control the on-screen virtual keyboard behavior on
    devices such as tablets, mobile phones, or other devices where a
    hardware keyboard may not be available for elements that also uses
    the [`contenteditable`](#contenteditable) attribute.

    -   `auto` or an *empty string*, which automatically shows the
        virtual keyboard when the element is focused or tapped.
    -   `manual`, which decouples focus and tap on the element from the
        virtual keyboard\'s state.

Specifications
--------------

  ------------------------------------------------------------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\# the-accesskey-attribute]](https://html.spec.whatwg.org/multipage/interaction.html#the-accesskey-attribute)

  [HTML Standard\
  [\# attr-autocapitalize]](https://html.spec.whatwg.org/multipage/interaction.html#attr-autocapitalize)

  [HTML Standard\
  [\# attr-fe-autocomplete]](https://html.spec.whatwg.org/multipage/form-control-infrastructure.html#attr-fe-autocomplete)

  [HTML Standard\
  [\# dom-fe-autofocus]](https://html.spec.whatwg.org/multipage/interaction.html#dom-fe-autofocus)

  [HTML Standard\
  [\# global-attributes:classes-2]](https://html.spec.whatwg.org/multipage/dom.html#global-attributes:classes-2)

  [HTML Standard\
  [\# attr-contenteditable]](https://html.spec.whatwg.org/multipage/interaction.html#attr-contenteditable)

  [HTML Standard\
  [\# attr-data-\*]](https://html.spec.whatwg.org/multipage/dom.html#attr-data-*)

  [HTML Standard\
  [\# the-dir-attribute]](https://html.spec.whatwg.org/multipage/dom.html#the-dir-attribute)

  [HTML Standard\
  [\# the-draggable-attribute]](https://html.spec.whatwg.org/multipage/dnd.html#the-draggable-attribute)

  [HTML Standard\
  [\# attr-enterkeyhint]](https://html.spec.whatwg.org/multipage/interaction.html#attr-enterkeyhint)

  [CSS Shadow Parts\
  [\# element-attrdef-html-global-exportparts]](https://drafts.csswg.org/css-shadow-parts/#element-attrdef-html-global-exportparts)

  [HTML Standard\
  [\# the-hidden-attribute]](https://html.spec.whatwg.org/multipage/interaction.html#the-hidden-attribute)

  [HTML Standard\
  [\# global-attributes:the-id-attribute-2]](https://html.spec.whatwg.org/multipage/dom.html#global-attributes:the-id-attribute-2)

  [HTML Standard\
  [\# the-inert-attribute]](https://html.spec.whatwg.org/multipage/interaction.html#the-inert-attribute)

  [HTML Standard\
  [\# attr-inputmode]](https://html.spec.whatwg.org/multipage/interaction.html#attr-inputmode)

  [HTML Standard\
  [\# attr-is]](https://html.spec.whatwg.org/multipage/custom-elements.html#attr-is)

  [HTML Standard\
  [\# attr-itemid]](https://html.spec.whatwg.org/multipage/microdata.html#attr-itemid)

  [HTML Standard\
  [\# names:-the-itemprop-attribute]](https://html.spec.whatwg.org/multipage/microdata.html#names:-the-itemprop-attribute)

  [HTML Standard\
  [\# attr-itemref]](https://html.spec.whatwg.org/multipage/microdata.html#attr-itemref)

  [HTML Standard\
  [\# attr-itemscope]](https://html.spec.whatwg.org/multipage/microdata.html#attr-itemscope)

  [HTML Standard\
  [\# attr-itemtype]](https://html.spec.whatwg.org/multipage/microdata.html#attr-itemtype)

  [HTML Standard\
  [\# attr-lang]](https://html.spec.whatwg.org/multipage/dom.html#attr-lang)

  [HTML Standard\
  [\# attr-nonce]](https://html.spec.whatwg.org/multipage/urls-and-fetching.html#attr-nonce)

  [CSS Shadow Parts\
  [\# part-attr]](https://drafts.csswg.org/css-shadow-parts/#part-attr)

  [HTML Standard\
  [\# the-popover-attribute]](https://html.spec.whatwg.org/multipage/popover.html#the-popover-attribute)

  [HTML Standard\
  [\# attr-popovertarget]](https://html.spec.whatwg.org/multipage/popover.html#attr-popovertarget)

  [HTML Standard\
  [\# attr-popovertargetaction]](https://html.spec.whatwg.org/multipage/popover.html#attr-popovertargetaction)

  [HTML Standard\
  [\# attr-slot]](https://html.spec.whatwg.org/multipage/dom.html#attr-slot)

  [DOM Standard\
  [\# ref-for-dom-element-slot①]](#)

  [HTML Standard\
  [\# attr-spellcheck]](https://html.spec.whatwg.org/multipage/interaction.html#attr-spellcheck)

  [HTML Standard\
  [\# the-style-attribute]](https://html.spec.whatwg.org/multipage/dom.html#the-style-attribute)

  [HTML Standard\
  [\# attr-tabindex]](https://html.spec.whatwg.org/multipage/interaction.html#attr-tabindex)

  [HTML Standard\
  [\# the-title-attribute]](https://html.spec.whatwg.org/multipage/dom.html#the-title-attribute)

  [HTML Standard\
  [\# attr-translate]](https://html.spec.whatwg.org/multipage/dom.html#attr-translate)

[VirtualKeyboard API\
  [\#
  dom-elementcontenteditable-virtualkeyboardpolicy]](https://w3c.github.io/virtual-keyboard/#dom-elementcontenteditable-virtualkeyboardpolicy)
  ------------------------------------------------------------------------------------------------------------------------------------------------------

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

`accesskey`

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

`autocapitalize`

43

79

111

No

30

No

43

43

111

30

5

4.0

`autocomplete`

14\[\"In Chrome 66, support was added for the `<textarea>` and
`<select>` elements.\", \"Originally only supported on the `<input>`
element.\", \"Chrome does not accept `off` as a value. See [bug
587466](https://crbug.com/587466).\"\]

≤79

4

No

≤12.1

6

4.4\[\"In Chrome 66, support was added for the `<textarea>` and
`<select>` elements.\", \"Originally only supported on the `<input>`
element.\", \"Chrome does not accept `off` as a value. See [bug
587466](https://crbug.com/587466).\"\]

18\[\"In Chrome 66, support was added for the `<textarea>` and
`<select>` elements.\", \"Originally only supported on the `<input>`
element.\", \"Chrome does not accept `off` as a value. See [bug
587466](https://crbug.com/587466).\"\]

4

≤12.1

6

1.0\[\"In Samsung Internet 9.0, support was added for the `<textarea>`
and `<select>` elements.\", \"Originally only supported on the `<input>`
element.\", \"Samsung Internet does not accept `off` as a value. See
[bug 587466](https://crbug.com/587466).\"\]

`autofocus`

79

1--79Supported for the `<button>`, `<input>`, `<select>`, and
`<textarea>` elements.

79

12--79Supported for the `<button>`, `<input>`, `<select>`, and
`<textarea>` elements.

1Supported for the `<button>`, `<input>`, `<select>`, and `<textarea>`
elements.

10Supported for the `<button>`, `<input>`, `<select>`, and `<textarea>`
elements.

66

≤12.1--66Supported for the `<button>`, `<input>`, `<select>`, and
`<textarea>` elements.

4Supported for the `<button>`, `<input>`, `<select>`, and `<textarea>`
elements.

79

≤37--79Supported for the `<button>`, `<input>`, `<select>`, and
`<textarea>` elements.

79

18--79Supported for the `<button>`, `<input>`, `<select>`, and
`<textarea>` elements.

4Supported for the `<button>`, `<input>`, `<select>`, and `<textarea>`
elements.

57

≤12.1--57Supported for the `<button>`, `<input>`, `<select>`, and
`<textarea>` elements.

3.2Supported for the `<button>`, `<input>`, `<select>`, and `<textarea>`
elements.

12.0

1.0--12.0Supported for the `<button>`, `<input>`, `<select>`, and
`<textarea>` elements.

`class`

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

`contenteditable`

1

12

3

5.5

9

≤4

4.4

18

4

14

≤3.2

1.0

`contextmenu`

No

No

9--85

No

No

No

No

No

32--56Support for the `contextmenu` attribute has been removed from
Firefox for Android (See [bug 1424252](https://bugzil.la/1424252)).

No

No

No

`data_attributes`

7

12

6

Yes

15

5.1

4.4

18

6

14

5

1.0

`dir`

1

79

1

No

15

≤4

4.4

18

4

14

≤3.2

1.0

`draggable`

4

12

2

Yes

12

5

4.4

18

4

14

4.2

1.0

`enterkeyhint`

77

79

94

No

66

13.1

77

77

94

57

13.4

12.0

`exportparts`

73

79

72

No

60

13.1

73

73

79

?

13.4

11.0

`hidden`

10

12

4

11

15

5.1

4

18

4

14

5

1.0

`id`

1

12

32

1--32`id` is a true global attribute only since Firefox 32.

Yes

15

1

4.4

18

32

4--32`id` is a true global attribute only since Firefox 32.

14

1

1.0

`inert`

102

102

112

No

88

15.5

102

102

112

70

15.5

19.0

`inputmode`

66

79

9517--23

No

53

No

66

66

79

47

12.2

9.0

`is`

67

79

63

No

54

No

67

67

63

48

No

9.0

`itemid`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`itemprop`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`itemref`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`itemscope`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`itemtype`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`lang`

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

`nonce`

Yes

Yes

31

No

Yes

Yes

Yes

Yes

31

Yes

Yes

Yes

`part`

73

79

72

No

60

13.1

73

73

79

52

13.4

11.0

`popover`

114

114

114

No

100

17

114

114

No

No

17

No

`popovertarget`

114

114

114

No

100

17

114

114

No

No

17

No

`popovertargetaction`

114

114

114

No

100

17

114

114

No

No

17

No

`slot`

53

≤79

63

No

40

10

53

53

63

41

10

6.0

`spellcheck`

9

12

Yes

11

Yes

Yes

47

47

57

37

9.3

5.0

`style`

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

`tabindex`

1

12

1.5

Yes

15

≤4

4.4

18

4

14

≤3.2

1.0

`title`

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

`translate`

19

79

111

No

15

6

4.4

25

111

14

6

1.5

`virtualkeyboardpolicy`

94

94

No

No

80

No

94

94

No

66

No

17.0

See also
--------

- [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element)
    interface that allows querying most global attributes.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes>>

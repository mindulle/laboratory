Pseudo-classes
==============

A [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
***pseudo-class*** is a keyword added to a selector that specifies a
special state of the selected element(s). For example, the pseudo-class
[`:hover`](:hover) can be used to select a button when a user\'s pointer
hovers over the button and this selected button can then be styled.

[css]

```css
/* Any button over which the user's pointer is hovering */
button:hover {
  color: blue;
}
```

A pseudo-class consists of a colon (`:`) followed by the pseudo-class
name (e.g., `:hover`). A functional pseudo-class also contains a pair of
parentheses to define the arguments (e.g., `:dir()`). The element that a
pseudo-class is attached to is defined as an *anchor element* (e.g.,
`button` in case `button:hover`).

Pseudo-classes let you apply a style to an element not only in relation
to the content of the document tree, but also in relation to external
factors like the history of the navigator ([`:visited`](:visited), for
example), the status of its content (like [`:checked`](:checked) on
certain form elements), or the position of the mouse (like
[`:hover`](:hover), which lets you know if the mouse is over an element
or not).

**Note:** In contrast to pseudo-classes,
[pseudo-elements](pseudo-elements.md) can be used to style a *specific
part* of an element.

Element display state pseudo-classes
------------------------------------

These pseudo-classes enable the selection of elements based on their
display states.

[`:fullscreen`](:fullscreen)

:   Matches an element that is currently in fullscreen mode.

[`:modal`](:modal)

:   Matches an element that is in a state in which it excludes all
    interaction with elements outside it until the interaction has been
    dismissed.

[`:picture-in-picture`](:picture-in-picture)

:   Matches an element that is currently in picture-in-picture mode.

Input pseudo-classes
--------------------

These pseudo-classes relate to form elements, and enable selecting
elements based on HTML attributes and the state that the field is in
before and after interaction.

[`:autofill`](:autofill)

:   Matches when an
    [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
    has been autofilled by the browser.

[`:enabled`](:enabled)

:   Represents a user interface element that is in an enabled state.

[`:disabled`](:disabled)

:   Represents a user interface element that is in a disabled state.

[`:read-only`](:read-only)

:   Represents any element that cannot be changed by the user.

[`:read-write`](:read-write)

:   Represents any element that is user-editable.

[`:placeholder-shown`](:placeholder-shown)

:   Matches an input element that is displaying placeholder text. For
    example, it will match the `placeholder` attribute in the
    [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
    and
    [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea)
    elements.

[`:default`](:default)

:   Matches one or more UI elements that are the default among a set of
    elements.

[`:checked`](:checked)

:   Matches when elements such as checkboxes and radio buttons are
    toggled on.

[`:indeterminate`](:indeterminate)

:   Matches UI elements when they are in an indeterminate state.

[`:blank`](:blank)

:   Matches a user-input element which is empty, containing an empty
    string or other null input.

[`:valid`](:valid)

:   Matches an element with valid contents. For example, an input
    element with the type \'email\' that contains a validly formed email
    address or an empty value if the control is not required.

[`:invalid`](:invalid)

:   Matches an element with invalid contents. For example, an input
    element with type \'email\' with a name entered.

[`:in-range`](:in-range)

:   Applies to elements with range limitations. For example, a slider
    control when the selected value is in the allowed range.

[`:out-of-range`](:out-of-range)

:   Applies to elements with range limitations. For example, a slider
    control when the selected value is outside the allowed range.

[`:required`](:required)

:   Matches when a form element is required.

[`:optional`](:optional)

:   Matches when a form element is optional.

[`:user-invalid`](:user-invalid)

:   Represents an element with incorrect input, but only when the user
    has interacted with it.

Linguistic pseudo-classes
-------------------------

These pseudo-classes reflect the document language and enable the
selection of elements based on language or script direction.

[`:dir()`](:dir)

:   The directionality pseudo-class selects an element based on its
    directionality as determined by the document language.

[`:lang()`](:lang)

:   Select an element based on its content language.

Location pseudo-classes
-----------------------

These pseudo-classes relate to links, and to targeted elements within
the current document.

[`:any-link`](:any-link)

:   Matches an element if the element would match either
    [`:link`](:link) or [`:visited`](:visited).

[`:link`](:link)

:   Matches links that have not yet been visited.

[`:visited`](:visited)

:   Matches links that have been visited.

[`:local-link`](:local-link)

:   Matches links whose absolute URL is the same as the target URL. For
    example, anchor links to the same page.

[`:target`](:target)

:   Matches the element which is the target of the document URL.

[`:target-within`](:target-within)

:   Matches elements which are the target of the document URL, but also
    elements which have a descendant which is the target of the document
    URL.

[`:scope`](:scope)

:   Represents elements that are a reference point for selectors to
    match against.

Resource state pseudo-classes
-----------------------------

These pseudo-classes apply to media that is capable of being in a state
where it would be described as playing, such as a video.

[`:playing`](:playing)

:   Represents a media element that is capable of playing when that
    element is playing.

[`:paused`](:paused)

:   Represents a media element that is capable of playing when that
    element is paused.

Time-dimensional pseudo-classes
-------------------------------

These pseudo-classes apply when viewing something which has timing, such
as a
[WebVTT](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API)
caption track.

[`:current`](:current)

:   Represents the element or ancestor of the element that is being
    displayed.

[`:past`](:past)

:   Represents an element that occurs entirely before the
    [`:current`](:current) element.

[`:future`](:future)

:   Represents an element that occurs entirely after the
    [`:current`](:current) element.

Tree-structural pseudo-classes
------------------------------

These pseudo-classes relate to the location of an element within the
document tree.

[`:root`](:root)

:   Represents an element that is the root of the document. In HTML this
    is usually the `<html>` element.

[`:empty`](:empty)

:   Represents an element with no children other than white-space
    characters.

[`:nth-child`](:nth-child)

:   Uses `An+B` notation to select elements from a list of sibling
    elements.

[`:nth-last-child`](:nth-last-child)

:   Uses `An+B` notation to select elements from a list of sibling
    elements, counting backwards from the end of the list.

[`:first-child`](:first-child)

:   Matches an element that is the first of its siblings.

[`:last-child`](:last-child)

:   Matches an element that is the last of its siblings.

[`:only-child`](:only-child)

:   Matches an element that has no siblings. For example, a list item
    with no other list items in that list.

[`:nth-of-type`](:nth-of-type)

:   Uses `An+B` notation to select elements from a list of sibling
    elements that match a certain type from a list of sibling elements.

[`:nth-last-of-type`](:nth-last-of-type)

:   Uses `An+B` notation to select elements from a list of sibling
    elements that match a certain type from a list of sibling elements
    counting backwards from the end of the list.

[`:first-of-type`](:first-of-type)

:   Matches an element that is the first of its siblings, and also
    matches a certain type selector.

[`:last-of-type`](:last-of-type)

:   Matches an element that is the last of its siblings, and also
    matches a certain type selector.

[`:only-of-type`](:only-of-type)

:   Matches an element that has no siblings of the chosen type selector.

User action pseudo-classes
--------------------------

These pseudo-classes require some interaction by the user in order for
them to apply, such as holding a mouse pointer over an element.

[`:hover`](:hover)

:   Matches when a user designates an item with a pointing device, such
    as holding the mouse pointer over the item.

[`:active`](:active)

:   Matches when an item is being activated by the user. For example,
    when the item is clicked on.

[`:focus`](:focus)

:   Matches when an element has focus.

[`:focus-visible`](:focus-visible)

:   Matches when an element has focus and the user agent identifies that
    the element should be visibly focused.

[`:focus-within`](:focus-within)

:   Matches an element to which [`:focus`](:focus) applies, plus any
    element that has a descendant to which [`:focus`](:focus) applies.

Functional pseudo-classes
-------------------------

These pseudo-classes accept a [](selector_list.md#selector_list) or [](selector_list.md#forgiving_selector_list) as a parameter.

[`:is()`](:is)

:   The matches-any pseudo-class matches any element that matches any of
    the selectors in the list provided. The list is forgiving.

[`:not()`](:not)

:   The negation, or matches-none, pseudo-class represents any element
    that is not represented by its argument.

[`:where()`](:where)

:   The specificity-adjustment pseudo-class matches any element that
    matches any of the selectors in the list provided without adding any
    specificity weight. The list is forgiving.

[`:has()`](:has)

:   The relational pseudo-class represents an element if any of the
    relative selectors match when anchored against the attached element.

Syntax
------

[css]

```css
selector:pseudo-class {
  property: value;
}
```

Like regular classes, you can chain together as many pseudo-classes as
you want in a selector.

Alphabetical index
------------------

Pseudo-classes defined by a set of CSS specifications include the
following:

A

- [`:active`](:active)
- [`:any-link`](:any-link)
- [`:autofill`](:autofill)

B

- [`:blank`](:blank) [Experimental]

C

- [`:checked`](:checked)
- [`:current`](:current) [Experimental]

D

- [`:default`](:default)
- [`:defined`](:defined)
- [`:dir()`](:dir) [Experimental]
- [`:disabled`](:disabled)

E

- [`:empty`](:empty)
- [`:enabled`](:enabled)

F

- [`:first`](:first)
- [`:first-child`](:first-child)
- [`:first-of-type`](:first-of-type)
- [`:fullscreen`](:fullscreen)
- [`:future`](:future) [Experimental]
- [`:focus`](:focus)
- [`:focus-visible`](:focus-visible)
- [`:focus-within`](:focus-within)

H

- [`:has()`](:has) [Experimental]
- [`:host`](:host)
- [`:host()`](:host)
- [`:host-context()`](:host-context) [Experimental]
- [`:hover`](:hover)

I

- [`:indeterminate`](:indeterminate)
- [`:in-range`](:in-range)
- [`:invalid`](:invalid)
- [`:is()`](:is)

L

- [`:lang()`](:lang)
- [`:last-child`](:last-child)
- [`:last-of-type`](:last-of-type)
- [`:left`](:left)
- [`:link`](:link)
- [`:local-link`](:local-link) [Experimental]

M

- [`:modal`](:modal)

N

- [`:not()`](:not)
- [`:nth-child()`](:nth-child)
- [`:nth-col()`](:nth-of-type) [Experimental]
- [`:nth-last-child()`](:nth-last-child)
- [`:nth-last-col()`](:nth-last-of-type)
    [Experimental]
- [`:nth-last-of-type()`](:nth-last-of-type)
- [`:nth-of-type()`](:nth-of-type)

O

- [`:only-child`](:only-child)
- [`:only-of-type`](:only-of-type)
- [`:optional`](:optional)
- [`:out-of-range`](:out-of-range)

P

- [`:past`](:past) [Experimental]
- [`:picture-in-picture`](:picture-in-picture)
- [`:placeholder-shown`](:placeholder-shown)
- [`:paused`](:paused)
- [`:playing`](:playing)

R

- [`:read-only`](:read-only)
- [`:read-write`](:read-write)
- [`:required`](:required)
- [`:right`](:right)
- [`:root`](:root)

S

- [`:scope`](:scope)
- [`:state()`]

T

- [`:target`](:target)
- [`:target-within`](:target-within) [Experimental]

U

- [`:user-invalid`](:user-invalid) [Experimental]

V

- [`:valid`](:valid)
- [`:visited`](:visited)

W

- [`:where()`](:where)

Specifications
--------------

  ----------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  pseudo-classes]](https://html.spec.whatwg.org/multipage/#pseudo-classes)

  [Selectors Level 4\
  ](https://drafts.csswg.org/selectors/)

[CSS Basic User Interface Module Level 4\
  ](https://drafts.csswg.org/css-ui/)
  ----------------------------------------------------------------------------------

See also
--------

- [Pseudo-elements](pseudo-elements.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes>

transition
==========

The `transition` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property is a [shorthand property](shorthand_properties.md) for
[`transition-property`](transition-property.md),
[`transition-duration`](transition-duration.md),
[`transition-timing-function`](transition-timing-function.md), and
[`transition-delay`](transition-delay.md).

Try it
------

Transitions enable you to define the transition between two states of an
element. Different states may be defined using
[pseudo-classes](pseudo-classes.md) like [`:hover`](:hover) or
[`:active`](:active) or dynamically set using JavaScript.

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`transition-delay`](transition-delay.md)
- [`transition-duration`](transition-duration.md)
- [`transition-property`](transition-property.md)
- [`transition-timing-function`](transition-timing-function.md)

Syntax
------

[css]

```css
/* Apply to 1 property */
/* property name | duration */
transition: margin-right 4s;

/* property name | duration | delay */
transition: margin-right 4s 1s;

/* property name | duration | easing function */
transition: margin-right 4s ease-in-out;

/* property name | duration | easing function | delay */
transition: margin-right 4s ease-in-out 1s;

/* Apply to 2 properties */
transition:
  margin-right 4s,
  color 1s;

/* Apply to all changed properties */
transition: all 0.5s ease-out;

/* Global values */
transition: inherit;
transition: initial;
transition: revert;
transition: revert-layer;
transition: unset;
```

The `transition` property is specified as one or more single-property
transitions, separated by commas.

Each single-property transition describes the transition that should be
applied to a single property (or the special values `all` and `none`).
It includes:

- zero or one value representing the property to which the transition
    should apply. This may be any one of:
  - the keyword `none`
  - the keyword `all`
  - a [`<custom-ident>`](custom-ident.md) naming a CSS property.
- zero or one [`<easing-function>`](easing-function.md) value
    representing the easing function to use
- zero, one, or two [`<time>`](time.md) values. The first value that can
    be parsed as a time is assigned to the
    [`transition-duration`](transition-duration.md), and the second value
    that can be parsed as a time is assigned to
    [`transition-delay`](transition-delay.md).

See [](using_css_transitions.md#when_property_value_lists_are_of_different_lengths)
when lists of property values aren\'t the same length. In short, extra
transition descriptions beyond the number of properties actually being
animated are ignored.

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](transition-delay.md): |
|                                   |     `0s`                          |
|                                   | -   [](transition-duration.md): |
|                                   |     `0s`                          |
|                                   | -   [](transition-property.md): |
|                                   |     all                           |
|                                   | -   [](transition-timing-function.md): |
|                                   |     `ease`                        |
+-----------------------------------+-----------------------------------+
| Applies to                        | all elements,                     |
|                                   | [`::before`](::before) and        |
|                                   | [`::after`](::after)              |
|                                   | [](pseudo-elements.md) |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | no                                |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](transition-delay.md): |
|                                   |     as specified                  |
|                                   | -   [](transition-duration.md): |
|                                   |     as specified                  |
|                                   | -   [](transition-property.md): |
|                                   |     as specified                  |
|                                   | -   [](transition-timing-function.md): |
|                                   |     as specified                  |
+-----------------------------------+-----------------------------------+
| Animation type                    | Not animatable                    |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
transition = 
  <single-transition>#  

<single-transition> = 
  [ none | <single-transition-property> ]  ||
  <time>                                   ||
  <easing-function>                        ||
  <time>                                   

<single-transition-property> = 
  all             |
  <custom-ident>  

<easing-function> = 
  linear                          |
  <linear-easing-function>        |
  <cubic-bezier-easing-function>  |
  <step-easing-function>          

<linear-easing-function> = 
  linear( <linear-stop-list> )  

<cubic-bezier-easing-function> = 
  ease                                                |
  ease-in                                             |
  ease-out                                            |
  ease-in-out                                         |
  cubic-bezier( <number [0,1]> , <number> , <number [0,1]> , <number> )  

<step-easing-function> = 
  step-start                                |
  step-end                                  |
  steps( <integer> [, <step-position> ]? )  

<linear-stop-list> = 
  [ <linear-stop> ]#  

<step-position> = 
  jump-start  |
  jump-end    |
  jump-none   |
  jump-both   |
  start       |
  end         

<linear-stop> = 
  <number>               &&
  <linear-stop-length>?  

<linear-stop-length> = 
  <percentage>  
```

Examples
--------

### Simple example

In this example, when the user hovers over the element, there is a
one-second delay before the four-second `font-size` transition occurs.

#### HTML

[html]

```html
<a class="target">Hover over me</a>
```

#### CSS

We include two [`<time>`](time.md) values. In the `transition` shorthand,
the first `<time>` value is the `transition-duration`. The second time
value is the `transition-delay`. Both default to `0s` if omitted.

[css]

```css
.target {
  font-size: 14px;
  transition: font-size 4s 1s;
}

.target:hover {
  font-size: 36px;
}
```

There are several more examples of CSS transitions included in the
[Using CSS transitions](using_css_transitions.md) article.

Specifications
--------------

  ------------------------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------------------------

  [CSS Transitions\
  [\#
  transition-shorthand-property]](https://drafts.csswg.org/css-transitions/#transition-shorthand-property)

  ------------------------------------------------------------------------------------------------------------------

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

`transition`

261

1212

49

16\[\"Before Firefox 57, transitions do not work when transitioning from
a
[`text-shadow`](https://developer.mozilla.org/docs/Web/CSS/text-shadow)
with a color specified to a `text-shadow` without a color specified (see
[bug 726550](https://bugzil.la/726550)).\", \"Before Firefox 57,
cancelling a filling animation (for example, with
`animation-fill-mode: forwards` set) can trigger a transition set on the
same element, although only once (see [bug
1192592](https://bugzil.la/1192592) and [these test
cases](https://bug1192592.bmoattachments.org/attachment.cgi?id=8843824)
for more information).\", \"Before Firefox 57, the
[`background-position`](https://developer.mozilla.org/docs/Web/CSS/background-position)
property can\'t be transitioned between two values containing different
numbers of
[`<position>`](https://developer.mozilla.org/docs/Web/CSS/position_value)
values, for example `background-position: 10px 10px;` and
`background-position: 20px 20px, 30px 30px;` (see [bug
1390446](https://bugzil.la/1390446)).\"\]

4

1010

1512.110.1--15

93.1

4.42

2618

49

16\[\"Before Firefox 57, transitions do not work when transitioning from
a
[`text-shadow`](https://developer.mozilla.org/docs/Web/CSS/text-shadow)
with a color specified to a `text-shadow` without a color specified (see
[bug 726550](https://bugzil.la/726550)).\", \"Before Firefox 57,
cancelling a filling animation (for example, with
`animation-fill-mode: forwards` set) can trigger a transition set on the
same element, although only once (see [bug
1192592](https://bugzil.la/1192592) and [these test
cases](https://bug1192592.bmoattachments.org/attachment.cgi?id=8843824)
for more information).\", \"Before Firefox 57, the
[`background-position`](https://developer.mozilla.org/docs/Web/CSS/background-position)
property can\'t be transitioned between two values containing different
numbers of
[`<position>`](https://developer.mozilla.org/docs/Web/CSS/position_value)
values, for example `background-position: 10px 10px;` and
`background-position: 20px 20px, 30px 30px;` (see [bug
1390446](https://bugzil.la/1390446)).\"\]

4

1412.110.1--14

92

1.51.0

`gradients`

No

12--79

No

10

No

preview

No

No

No

No

No

No

`transition_behavior_value`

117

117

No

No

103

No

117

117

No

No

No

No

See also
--------

- [Using CSS transitions](using_css_transitions.md)
- [`TransitionEvent`](https://developer.mozilla.org/en-US/docs/Web/API/TransitionEvent)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/transition>

# Markup And Styling

## [[_Resources/Markup And Styling/html/index|HTML]]

### [[_Resources/Markup And Styling/html/element/index|Elements]]

- **Main root**: `<html>`
- **Document metadata**: `<base>`, `<head>`, `<link>`, `<meta>`, `<style>`, `<title>`
- **Sectioning root**: `<body>`
- **Content sectioning**: `<address>`, **`<article>`**, `<aside>`, **`<footer>`**, **`<header>`**, **`<h1> ~ <h6>`**, `<hgroup>`, **`<main>`**, **`<nav>`**, **`<section>`**, `<search>`
- **Text content**: `<blockqoute>`, `<dd>`, **`<div>`**, `<dl>`, `<dt>`, **`<figcaption>`**, `<figure>`, `<hr>`, **`<li>`**, `<menu>`, **`<ol>`**, **`<p>`**, **`<pre>`**, **`<ul>`**
- **Inline text semantics**: **`<a>`**, `<abbr>`, `<b>`, `<bdi>`, `<bdo>`, `<br>`, `<cite>`, **`<code>`**, `<data>`, `<dfn>`, `<em>`, `<i>`, `<kbd>`, `<mark>`, `<q>`, `<rp>`, `<rt>`, `<ruby>`, `<s>`, `<samp>`, `<small>`, **`<span>`**, **`<strong>`**, `<sub>`, `<sup>`, `<time>`, `<u>`, `<var>`, `<wbr>`
- **Image and multimedia**: `<area>`, **`<audio>`**, **`<img>`**, `<map>`, `<track>`, **`<video>`**
- **Embedded content**: `<embed>`, **`<iframe>`**, `<object>`, `<picture>`, `<portal>`, `<source>`
- **SVG and MathML**: **`<svg>`**, `<math>`
- **Scripting**: **`<canvas>`**, `<noscript>`, **`<script>`**
- Demarcating edits: `<del>`, `<ins>`
- **Table content**: **`<caption>`**, `<col>`, `<colgroup>`, **`<table>`**, **`<tbody>`**, **`<td>`**, `<tfoot>`, **`<th>`**, **`<thead>`**, **`<tr>`**
- **Forms**: **`<button>`**, `<datalist>`, **`<fieldset>`**, **`<form>`**, **`<input>`**, **`<label>`**, `<legend>`, `<meter>`, `<optgroup>`, `<option>`, `<output>`, `<progress>`, `<select>`, `<textarea>`
- **Interactive elements**: **`<details>`**, `<dialog>`, **`<summary>`**
- Web Components: **`<slot>`**, `<template>`

### [[_Resources/Markup And Styling/html/attributes/index|Attributes]]
| input        | form             | Global Attributes | align Deprecated | iframe                                                       | script                                                                                                                                                  |
| ------------ | ---------------- | ----------------- | ---------------- | ------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| textarea     | video            | background        | bgcolor          | border                                                       | meta                                                                                                                                                    |
| q            | Global Attribute | color             | th               | menu element which will serve as the element's context menu. | area                                                                                                                                                    |
| object       | time             | img               | track            | contenteditable                                              | output                                                                                                                                                  |
| form.        | form owner.      | height            | meter            | link                                                         | loading Experimental                                                                                                                                    |
| html element | progress         | style             | select           | param                                                        | dialog                                                                                                                                                  |
| ol           | option           | source            | colgroup         | table                                                        | div, this is a legacy attribute, in which case the CSS [width](https://developer.mozilla.org/en-US/docs/Web/CSS/width) property should be used instead. |

### [[_Resources/Markup And Styling/html/global_attributes/index|Global Attributes]]
#### Event Handler Attributes:
| onabort          | onautocomplete | onautocompleteerror | onblur       | oncancel         | oncanplay   | oncanplaythrough | onchange     |
| ---------------- | -------------- | ------------------- | ------------ | ---------------- | ----------- | ---------------- | ------------ |
| onclick          | onclose        | oncontextmenu       | oncuechange  | ondblclick       | ondrag      | ondragend        | ondragenter  |
| ondragleave      | ondragover     | ondragstart         | ondrop       | ondurationchange | onemptied   | onended          | onerror      |
| onfocus          | oninput        | oninvalid           | onkeydown    | onkeypress       | onkeyup     | onload           | onloadeddata |
| onloadedmetadata | onloadstart    | onmousedown         | onmouseenter | onmouseleave     | onmousemove | onmouseout       | onmouseover  |
| onmouseup        | onmousewheel   | onpause             | onplay       | onplaying        | onprogress  | onratechange     | onreset      |
| onresize         | onscroll       | onseeked            | onseeking    | onselect         | onshow      | onsort           | onstalled    |
| onsubmit         | onsuspend      | ontimeupdate        | ontoggle     | onvolumechange   | onwaiting   |                  |              |
#### Global Attributes Lists:
| accesskey | autocapitalize | autofocus             | class        | contenteditable | contextmenu |
| --------- | -------------- | --------------------- | ------------ | --------------- | ----------- |
| data-*    | dir            | draggable             | enterkeyhint | exportparts     | hidden      |
| id        | inert          | inputmode             | is           | itemid          | itemprop    |
| itemref   | itemscope      | itemtype              | lang         | nonce           | part        |
| popover   | role           | slot                  | spellcheck   | style           | tabindex    |
| title     | translate      | virtualkeyboardpolicy |              |                 |             |

### [[content_categories|Content Categories]]
#### Main content categories
##### Metadata content
- `<base>`, `<link>`, `<meta>`, `<noscript>`, `<script>`,`<style>`, `<title>`
##### Flow content
| `<a>`                                                  | `<abbr>`                                       | `<address>`                                     | `<article>`                                                 | `<aside>`  | `<audio>`    | `<b>`        | `<bdo>`      | `<bdi>`     | `<blockquote>` |
| ------------------------------------------------------ | ---------------------------------------------- | ----------------------------------------------- | ----------------------------------------------------------- | ---------- | ------------ | ------------ | ------------ | ----------- | -------------- |
| `<br>`                                                 | `<button>`                                     | `<canvas>`                                      | `<cite>`                                                    | `<code>`   | `<data>`     | `<datalist>` | `<del>`      | `<details>` | `<dfn>`        |
| `<dialog>`                                             | `<div>`                                        | `<dl>`                                          | `<em>`                                                      | `<embed>`  | `<fieldset>` | `<figure>`   | `<footer>`   | `<form>`    | h1             |
| h2                                                     | h3                                             | h4                                              | h5                                                          | h6         | `<header>`   | `<hgroup>`   | `<hr>`       | `<i>`       | `<iframe>`     |
| `<img>`                                                | `<input>`                                      | `<ins>`                                         | `<kbd>`                                                     | `<label>`  | `<main>`     | `<map>`      | `<mark>`     | `<math>`    | `<menu>`       |
| `<meter>`                                              | `<nav>`                                        | `<noscript>`                                    | `<object>`                                                  | `<ol>`     | `<output>`   | `<p>`        | `<picture>`  | `<pre>`     | `<progress>`   |
| `<q>`                                                  | `<ruby>`                                       | `<s>`                                           | `<samp>`                                                    | `<search>` | `<script>`   | `<section>`  | `<select>`   | `<slot>`    | `<small>`      |
| `<span>`                                               | `<strong>`                                     | `<sub>`                                         | `<sup>`                                                     | `<svg>`    | `<table>`    | `<template>` | `<textarea>` | `<time>`    | `<u>`          |
| `<ul>`                                                 | `<var>`                                        | `<video>`                                       | `<wbr>`                                                     | Plain text |              |              |              |             |                |
| `<area>`, if it is a descendant of a `<map>`  element. | `<link>`, if the itemprop attribute is present | `<meta>`, if the  itemprop attribute is present | `<style>`, if the `scoped` Deprecated attribute is presentt |            |              |              |              |             |                |
##### Sectioning content
- `<header>` elements, `<footer>`, `<article>`, `<aside>`, `<nav>`, and `<section>`.
##### Heading content
- `<h1> ~ <h6>`  , `<hgroup>`
##### Phrasing content
| `<abbr>`                                                                 | `<audio>`                                            | `<b>`                                         | `<bdi>`                                       | `<bdo>`                                        | `<br>`                                        | `<button>`                                     | `<canvas>` |
| ------------------------------------------------------------------------ | ---------------------------------------------------- | --------------------------------------------- | --------------------------------------------- | ---------------------------------------------- | --------------------------------------------- | ---------------------------------------------- | ---------- |
| `<cite>`                                                                 | `<code>`                                             | `<data>`                                      | `<datalist>`                                  | `<dfn>`                                        | `<em>`                                        | `<embed>`                                      | `<i>`      |
| `<iframe>`                                                               | `<img>`                                              | `<input>`                                     | `<kbd>`                                       | `<label>`                                      | `<mark>`                                      | `<math>`                                       | `<meter>`  |
| `<noscript>`                                                             | `<object>`                                           | `<output>`                                    | `<picture>`                                   | `<progress>`                                   | `<q>`                                         | `<ruby>`                                       | `<s>`      |
| `<samp>`                                                                 | `<script>`                                           | `<select>`                                    | `<slot>`                                      | `<small>`                                      | `<span>`                                      | `<strong>`                                     | `<sub>`    |
| `<sup>`                                                                  | `<svg>`                                              | `<template>`                                  | `<textarea>`                                  | `<time>`                                       | `<u>`                                         | `<var>`                                        | `<video>`  |
| `<wbr>` and plain text (not only consisting of white spaces characters). |                                                      |                                               |                                               |                                                |                                               |                                                |            |
| `<a>`, if it contains only phrasing content                              | `<area>`, if it is a descendant of a `<map>` element | `<del>`, if it contains only phrasing content | `<ins>`, if it contains only phrasing content | `<link>`, if the itemprop attribute is present | `<map>`, if it contains only phrasing content | `<meta>`, if the itemprop attribute is present |            |

##### Embedded content
| `<audio>` | `<canvas>` | `<embed>`   | `<iframe>` | `<img>`   |
| --------- | ---------- | ----------- | ---------- | --------- |
| `<math>`  | `<object>` | `<picture>` | `<svg>`    | `<video>` |
##### Interactive content
| `<button>`                 | `<details>`                                       | `<embed>`                    | `<iframe>`                                     | `<label>`                                        | `<select>`.                                       |
| -------------------------- | ------------------------------------------------- | ---------------------------- | ---------------------------------------------- | ------------------------------------------------ | ------------------------------------------------- |
| `<a>` attribute is present | `<audio>`, if the `controls` attribute is present | `<img>` attribute is present | `<input>` attribute is not in the hidden state | `<object>`, if the `usemap` attribute is present | `<video>`, if the `controls` attribute is present |
##### Form-associated content
| form owner     | A form owner is either the containing [`<form>`](element/form) element or the element whose id is specified in the **form** attribute.                            | `<button>`, `<fieldset>`, `<input>`, `<label>`, `<meter>`, `<object>`, `<output>`, `<progress>`, `<select>`, `<textarea>` |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| sub-categories | Elements that are listed in the [`form.elements`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/elements) and `fieldset.elements` collections. | `<button>`, `<input>`, `<output>`, `<textarea>`                                                                           |
| labelable      | Elements that can be associated with `<label>` elements.                                                                                                          | `<button>`, `<input>`, `<output>`, `<select>`                                                                             |
| submittable    | Elements that can be used for constructing the form data set when the form is submitted.                                                                          | `<button>`, `<input>`, `<select>`                                                                                         |
| resettable     | Elements that can be affected when a form is reset.                                                                                                               | `<input>`, `<output>`,`<select>`, `<textarea>`                                                                            |
#### Days of the month
| Month number | Name (English) | Length in days        |
| ------------ | -------------- | --------------------- |
| 1            | January        | 31                    |
| 2            | February       | 28 (29 in leap years) |
| 3            | March          | 31                    |
| 4            | April          | 30                    |
| 5            | May            | 31                    |
| 6            | June           | 30                    |
| 7            | July           | 31                    |
| 8            | August         | 31                    |
| 9            | September      | 30                    |
| 10           | October        | 31                    |
| 11           | November       | 30                    |
| 12           | December       | 31                    |
#### Examples
- `strings`: 2005-06-07, 8:45, 8:45:25, 1933-08-04 3:40, 1977-04-01 14:00:30, 1901-01-01T00:00Z, 1901-01-01T00:00:01-04:00,
- `week string`: 2001-W37, 1953-W01, 1948-W53, 1949-W01, 0531-W16, 0042-W04
- `month string`: 17310-09, 2019-01, 1993-11, 0571-04, 2001-07
- `date string`: 1993-11-01, 1066-10, 0571-4, 1962-02
- `time string`: 0:00:31, 12:15, 13:44:25
- `Local date and time strings`: 1986-01-28T11:38:00.01, 1986-01-28 11:38:00.010, 0170-07-31T22:00:00
- `Global date and time strings`: 2005-06-07T00:00Z, 1789-08-22T12:30:00.1-04:00, 3755-01-01 00:00+10:00
### Advanced topics
[[cors_enabled_image|CORS enabled image]]
- The [[crossorigin]] attribute, in combination with an appropriate [CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS) header, allows images defined by the [[img|<img>]] element to be loaded from foreign origins and used in a [[canvas|<canvas>]] element as if they were being loaded from the current origin.
  
[[crossorigin|CORS settings attributes]]
- Some HTML elements that provide support for [CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS), such as [[img|<img>]] or [[video|<video>]], have a `crossorigin` attribute (`crossOrigin` property), which lets you configure the CORS requests for the element's fetched data.
  
[[preload|Preloading content with rel="preload"]]
- The `preload` value of the [[link|<link>]] element's [[rel]] attribute allows you to write declarative fetch requests in your HTML [[head|<head>]], specifying resources that your pages will need very soon after loading, which you therefore want to start preloading early in the lifecycle of a page load, before the browser's main rendering machinery kicks in. This ensures that they are made available earlier and are less likely to block the page's first render, leading to performance improvements. This article provides a basic guide to how `preload` works.

## [[_Resources/Markup And Styling/css/index|CSS]]
### [[_Resources/Markup And Styling/css/index#Syntax and semantics|Syntax]]
| Syntax                                         | Literals or Example                                           | Syntax                                                                                                 | Literals                               |
| ---------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------ | -------------------------------------- |
| [[at-rule\|At-rules]]                          | `@identifier (RULE) {}`                                       | [[_Resources/Markup And Styling/css/syntax#CSS declarations\|CSS syntax - declarations]]               | `:`                                    |
| [[comments\|Comments]]                         | `/* Comment */`                                               | [[_Resources/Markup And Styling/css/syntax#CSS declaration blocks \| CSS syntax - declaration blocks]] | `{}`                                   |
| [[inheritance\|Inheritance]]                   | `em {border: inherit;}`                                       | [[_Resources/Markup And Styling/css/syntax#CSS rulesets \| CSS syntax - rules and ruleset]]            | starts with `@`                        |
| [[shorthand_properties\|Shorthand properties]] | `margin: 10px 5px 10px 5px;`                                  | [[_Resources/Markup And Styling/css/syntax#CSS statements \| CSS syntax - statements]]                 | ends with `;`                          |
| [[css_functions\|CSS functional notations]]    | `selector { property: function([argument]? [, argument]!); }` | [[value_definition_syntax#Component value combinators\|Value definition syntax - combinators]]         | ` `,`&&`,`\|\|`,`\|`,`[ ]`,            |
|                                                |                                                               | [[value_definition_syntax#Component value multipliers\|Value definition syntax - multipliers]]         | ` `, `*`, `+`, `?`, `{A,B}` ,`#` , `!` |
### Semantics
- [[cascade#Complete cascade order|Cascade order]] : The **cascade** is an algorithm that defines how user agents combine property values originating from different sources.
- [Descriptor](https://developer.mozilla.org/en-US/docs/Glossary/CSS_Descriptor): A **CSS descriptor** defines the characteristics of an [at-rule](https://developer.mozilla.org/en-US/docs/Web/CSS/At-rule). At-rules may have one or multiple descriptors. Each descriptor has:
  - A name,
  - A value, which holds the component values,
  - An `!important` flag, which in its default state is unset.
- [[specificity#Selector weight categories|Specificity]]: **Specificity** is the algorithm used by browsers to determine the [CSS declaration](https://developer.mozilla.org/en-US/docs/Learn/CSS/First_steps/What_is_CSS#css_syntax) that is the most relevant to an element, which in turn, determines the property value to apply to the element.
- [[css_values_and_units#Distance units|CSS unit and value types]]: Every CSS declaration includes a property / value pair.

### [[_Resources/Markup And Styling/css/index#Selectors|Selectors]]
| Basic selectors         | Literals       | Grouping selectors | Literals |
| ----------------------- | -------------- | ------------------ | -------- |
| [[universal_selectors]] | `*`            | [[selector_list]]  | `A, B`   |
| [[type_selectors]]      | `elementname`  |                    |          |
| [[class_selectors]]     | `.classname`   |                    |          |
| [[id_selectors]]        | `#idname`      |                    |          |
| [[attribute_selectors]] | `[attr=value]` |                    |          |

| Combinators | Literals | Pseudo | Literals |
| ---- | ---- | ---- | ---- |
| [[next-sibling_combinator]] | `A + B` | [[pseudo-classes]] | `:` |
| [[subsequent-sibling_combinator]] | `A ~ B` | [[pseudo-elements]] | `::` |
| [[child_combinator]] | `A > B` |  |  |
| [[descendant_combinator]] | `A B` |  |  |
| [[column_combinator]] | `A \|\| B` (Experimental) |  |  |

### [[_Resources/Markup And Styling/css/index#DOM-CSS / CSSOM|DOM-CSS / CSSOM]]
| Major object types 1                                                                            | Major object types 2                                                                      | Important method                                                                                          |
| ----------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| [`Document.styleSheets`](https://developer.mozilla.org/en-US/docs/Web/API/Document/styleSheets) | [`HTMLElement.style`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/style) | [`CSSStyleSheet.insertRule()`](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleSheet/insertRule) |
| `styleSheets[i].cssRules`                                                                       | `HTMLElement.style.cssText` (just style)                                                  | [`CSSStyleSheet.deleteRule()`](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleSheet/deleteRule) |
| `cssRules[i].cssText` (selector & style)                                                        | [`Element.className`](https://developer.mozilla.org/en-US/docs/Web/API/Element/className) |                                                                                                           |
| `cssRules[i].selectorText`                                                                      | [`Element.classList`](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList) |                                                                                                           |

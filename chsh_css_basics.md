# Basic CSS

* TOC (placeholder for the automatic creation of a Table of contents)
{:toc}

### Selectors

| Selector            | Description       |
| ------------------- | ----------------- |
| `*`                 | All elements      |
| `div`               | Element           |
| `.class`            | Class             |
| `#id`               | ID                |
| `[disabled]`        | Attribute         |
| `[role="status"]`   | Attribute         |

### Combinators

| Example                  | Combinator Type           | Description                                                  |
| ------------------------ | ------------------------- | ------------------------------------------------------------ |
| `div p`                  | Descendant Combinator      | Selects all `<p>` elements inside a `<div>`                 |
| `div > p`                | Child Combinator           | Selects all `<p>` elements that are a direct child of a `<div>` |
| `h2 + p`                 | Adjacent Sibling Combinator| Selects the `<p>` element that is immediately preceded by an `<h2>` element |
| `h2 ~ p`                 | General Sibling Combinator | Selects all `<p>` elements that are siblings of an `<h2>` element |
| `*`                      | Universal Selector         | Selects all elements                                        |
| `h1, h2, h3`             | Grouping                   | Selects all `<h1>`, `<h2>`, and `<h3>` elements              |
| `section article > h2`   | Multiple Combinators       | Selects `<h2>` elements that are direct children of `<article>` elements inside a `<section>` |

> #### Combinator Summary
> 
> - **Descendant (` `):** Selects all matching descendants.
> - **Child (`>`):** Selects only direct children.
> - **Adjacent Sibling (`+`):** Selects the element immediately preceded by another.
> - **General Sibling (`~`):** Selects all siblings.

### Attribute selector

| Selector                       | Example                  | Description                                          |
| ------------------------------ | ------------------------ | ---------------------------------------------------- |
| `[attribute]`                  | `[target]`              | Selects elements with the specified attribute        |
| `[attribute=value]`            | `[target="_blank"]`     | Selects elements with a specific attribute value     |
| `[attribute~=value]`           | `[class~="important"]`  | Selects elements with an attribute containing a specific word in a space-separated list |
| `[attribute|=value]`           | `[lang|="en"]`          | Selects elements with a specific value for the given attribute followed by a hyphen or at the end of the attribute value |
| `[attribute^=value]`           | `[href^="https://"]`    | Selects elements with an attribute value that starts with a specified value |
| `[attribute$=value]`           | `[src$=".jpg"]`         | Selects elements with an attribute value that ends with a specified value |
| `[attribute*=value]`           | `[title*="example"]`    | Selects elements with an attribute value containing a specified substring |
| `[attribute operator value i]` | `[alt="flower" i]`      | Selects elements with a case-insensitive attribute value for required operator |

### Pseudo elements

A CSS pseudo-element is used to style specified parts of an element.

| Selector           | Example          | Example Description                                               |
| ------------------- | -----------------| ------------------------------------------------------------------ |
| `::after`           | `p::after`       | Insert something after the content of each `<p>` element          |
| `::before`          | `p::before`      | Insert something before the content of each `<p>` element         |
| `::first-letter`    | `p::first-letter`| Selects the first letter of each `<p>` element                     |
| `::first-line`      | `p::first-line`  | Selects the first line of each `<p>` element                       |
| `::marker`          | `::marker`       | Selects the markers of list items                                  |
| `::selection`       | `p::selection`   | Selects the portion of an element that is selected by a user      |

### Pseudo classes

A pseudo-class is used to define a special state of an element.

| Selector                | Example                 | Example Description                                                       |
| ----------------------- | ----------------------- | -------------------------------------------------------------------------- |
| `:active`               | `a:active`              | Selects the active link                                                   |
| `:checked`              | `input:checked`         | Selects every checked `<input>` element                                   |
| `:disabled`             | `input:disabled`        | Selects every disabled `<input>` element                                  |
| `:empty`                | `p:empty`               | Selects every `<p>` element that has no children                          |
| `:enabled`              | `input:enabled`         | Selects every enabled `<input>` element                                   |
| `:first-child`          | `p:first-child`         | Selects every `<p>` element that is the first child of its parent         |
| `:first-of-type`        | `p:first-of-type`       | Selects every `<p>` element that is the first `<p>` element of its parent  |
| `:focus`                | `input:focus`           | Selects the `<input>` element that has focus                              |
| `:hover`                | `a:hover`               | Selects links on mouse over                                               |
| `:in-range`             | `input:in-range`        | Selects `<input>` elements with a value within a specified range           |
| `:invalid`              | `input:invalid`         | Selects all `<input>` elements with an invalid value                      |
| `:lang(language)`       | `p:lang(it)`            | Selects every `<p>` element with a lang attribute value starting with "it" |
| `:last-child`           | `p:last-child`          | Selects every `<p>` element that is the last child of its parent          |
| `:last-of-type`         | `p:last-of-type`        | Selects every `<p>` element that is the last `<p>` element of its parent  |
| `:link`                 | `a:link`                | Selects all unvisited links                                               |
| `:not(selector)`        | `:not(p)`               | Selects every element that is not a `<p>` element                         |
| `:nth-child(n)`         | `p:nth-child(2)`        | Selects every `<p>` element that is the second child of its parent        |
| `:nth-last-child(n)`    | `p:nth-last-child(2)`   | Selects every `<p>` element that is the second child of its parent, counting from the last child |
| `:nth-last-of-type(n)`  | `p:nth-last-of-type(2)` | Selects every `<p>` element that is the second `<p>` element of its parent, counting from the last child |
| `:nth-of-type(n)`       | `p:nth-of-type(2)`      | Selects every `<p>` element that is the second `<p>` element of its parent |
| `:only-of-type`         | `p:only-of-type`        | Selects every `<p>` element that is the only `<p>` element of its parent |
| `:only-child`           | `p:only-child`          | Selects every `<p>` element that is the only child of its parent, excluding text and comments |
| `:optional`             | `input:optional`        | Selects `<input>` elements with no "required" attribute                   |
| `:out-of-range`         | `input:out-of-range`    | Selects `<input>` elements with a value outside a specified range         |
| `:read-only`            | `input:read-only`       | Selects `<input>` elements with a "readonly" attribute specified          |
| `:read-write`           | `input:read-write`      | Selects `<input>` elements with no "readonly" attribute                    |
| `:required`             | `input:required`        | Selects `<input>` elements with a "required" attribute specified          |
| `:root`                 | `:root`                 | Selects the document's root element                                        |
| `:target`               | `#news:target`          | Selects the current active #news element (clicked on a URL containing that anchor name) |
| `:valid`               | `input:valid`          | Selects all `<input>` elements with a valid value                           |
| `:visited`             | `a:visited`            | Selects all visited links                                                 |


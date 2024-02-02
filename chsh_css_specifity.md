# CSS specificity

* TOC (placeholder for the automatic creation of a Table of contents)
{:toc}

### Specificity Hierarchy

1. **Inline Styles:** `style` attribute on an HTML element.

2. **ID Selectors:** `#id` selector.

3. **Class Selectors, Attribute Selectors, Pseudo-classes:** `.class`, `[attribute]`, `:hover`, etc.

4. **Type Selectors, Pseudo-elements:** `element`, `p`, `div`, `::before`, `::after`, etc.

5. **Universal Selector:** `*` selector.

### How Specificity is Calculated

- Count the number of:
  - IDs in the selector.
  - Classes, attributes, and pseudo-classes in the selector.
  - Elements and pseudo-elements in the selector.

- Write the specificity as a four-part number (e.g., `0-1-3-1` for an ID, 3 classes, and an element).

### Examples

- `#header` has specificity `0-1-0-0` (1 ID).
- `ul.navbar li a:active` has specificity `0-1-3-1` (1 class, 3 elements, 1 pseudo-class).
- `body::before` has specificity `0-0-0-2` (1 element, 1 pseudo-element).
- `#footer .info p::after` has specificity `0-1-3-2` (1 ID, 1 class, 1 element, 1 pseudo-element).

### Important Notes

- **!important:** Overrides normal specificity rules.
- **Styles with the same specifity:** The last property declared takes precedence.

### Calculating Specificity

1. Count the number of IDs in the selector.
2. Count the number of classes, attributes, and pseudo-classes in the selector.
3. Count the number of elements and pseudo-elements in the selector.
4. Combine these numbers into a four-part specificity value (e.g., `0-1-3-0`).


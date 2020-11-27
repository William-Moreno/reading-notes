# Styling with CSS

---

## The Basics

Imagine there is a box around every HTML element on a webpage. CSS controls the way each of those boxes is presented on the page. CSS associates style rules with HTML elements. Rules are structured as follows:

```
h1 {color: red;}
```

_This rule changes to color of 'heading 1' text to red._

- A CSS rule consists of a selector and a declaration. In this case, the selector is `h1` and the declaration within the {} brackets is `color: red;`
- Selectors determine which element or elements the rule applies to.
- Declarations indicate the styling to apply to the selected element. They consist of one or more properties and their desired values.

## Internal CSS versus External CSS

CSS can be internal or external _(sometimes even both)_ to the HTML document. However, the vastly preferred method is external.

- **Internal** - The CSS is written inside `<style>` tags, usually located in the `<head>` of the HTML document. It is typically used in single page websites when it is used.
- **External** - The CSS for the HTML document is located in a separate file. A `<link>` element is added to the HTML document, usually in the `<head>`, to tell the browser where to find the styling file for the webpage. Keeping the CSS in its own file keeps code cleaner and less cluttered. It also makes it easier to style multiple pages of a single site, because each separate HTML document can reference the same CSS file.

## Common CSS Selectors

| **Selector Type** | **Matched Target**                                | **Example**        |
| ----------------- | ------------------------------------------------- | ------------------ |
| _universal_       | all elements on page                              | **\***             |
| _type_            | element names                                     | **h1, p, article** |
| _class_           | elements with specified class attribute           | **.class**         |
| _ID_              | elements with specified id attribute              | **\#id**           |
| _descendant_      | elements which are descendants of another element | **li>a**           |

## CSS Rules Cascade

A hierarcy exists to govern application of conflicting CSS rules for the same targeted element.

- If two selectors are identical the last rule entered will take precedence
- If a selector is more specific than the other, it will take precedence
  - if `!important` is added to the end of a declaration, it will always take precedence

## Inheritance

Some CSS properties are inherited and others are uninherited. Inherited rules apply to the child elements of an element.

- Examples of inherited properties are:

  - font-family
  - color

- Examples of properties which are not inherited are:
  - background-color
  - border properties

## Quirks

Different operating systems and browsers _(especially older or less-used ones)_ can cause your page styling to differ from what you planned. When this happens, it's often called a "CSS Bug" or a "browser quirk".

# Colors

When selecting colors for an element, they can be specified in several ways. However, the three most common are:

- **RGB** - Red, green and blue values ranging from 0 to 255.
- **Hex Codes** - A \# followed by a 6-digit code.
- **Color Names** - One of 147 preset colors recognized by browsers.

Colors can be apply to different things.

The `color` property sets the color of foreground items such as text.
The `background-color` property sets the color of the background of a particular element.

## Contrast

It is important to select text and background colors that provide enough contrast to be legible.

- **low contrast** - harder to read, particularly for the visually impaired or color blind
- **high contrast** - easier to read, but if there is a lot of text to be read, it can make it harder too
- **medium contrast** - improves readability for longer spans of text

## Opacity

Using color indicators like `rgba` or `hsla`, allows you to specify the opacity of a color. The "a" position is a value between 0.0 and 1.0 that represents a percentage of transparency. Some browsers may not support opacity so it is good practice to create an alternate backup CSS rule above the rule that those browsers can use.

[Back to Main](../README.md)

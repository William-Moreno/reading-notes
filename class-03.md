# HTML Lists, CSS Boxes and JavaScript Control Flow
---
## HTML Lists

There are tree types of list elements in HTML which are all indented by default when rendered in the browser:
1. **Ordered Lists** - `<ol>` - The list entries (`<li>`) in these lists are preceded by numbers. An example for use might be the steps of a baking recipe.
1. **Unordered Lists** - `<ul>` - The list entries (`<li>`) in these lists are preceded by bullets. An example for usse might be the list of ingredients for the previously mentioned baking recipe.
1. **Definition Lists** - `<dl>` - The entries for these lists come in pairs *(typically)* of `<dt>` and `<dd>` elements. The `<dt>` elements are indented once and represent the defined term. The `<dd>` elements are further indented and represent the definition(s) of the defined terms.

Lists can also be nested inside of other lists...

```HTML
<ul>
    <li>item a</li>
    <li>item b</li>
    <li>item c</li>
        <ul>
            <li>sub-item 1</li>
            <li>sub-item 2</li>
        </ul>
    <li> item d</li>
</ul>
```

## CSS Boxes
CSS treaats all HTML elements like they are all contained in their own individual boxes for purposes of styling. Several properties can be used to alter the appearance of these "boxes".

### Dimensions
By default, a box is sized just large enough to hold the contained content. However, these defaults can be overridden.
- **width, min-width, max-width** - The width of the box can be set to a specific dimension and/or limited to the smallest or largest allowable width for the box.
- **height, min-height, max-height** - The height of the box can be set to a specific dimension and/or limited to the smallest or largest allowable height for the box.

If the height and width designated for a box is too small to hold all of the content, the content will expand out of the box and look messy. When this occurs, the **overflow** property can control what happens in a couple of ways:
- **hidden** - This value simply hides any content that does not fit inside the box.
- **scroll** - This value adds a scroll bar to the box to allow users to scroll and see the non-visible content.

### Border, Margin & Padding
Every "box" has these three properties. 
- **Border** - Every box has one even if it is not visible. It separates the edge of one box from another. The border-width property can be set in pixels or with the values: *thin, medium,* or *thick*. Percentages will not work here. Border-style can be set to a number of values including: solid, dashed or inset. border-color can be set in the same manner as text color, background color, etc. Border properties can be set with a single value, various values can be set for any of the 'trouble'*(TRBL)* directions: -top, -right, -bottom, -left, or the width, style and color of the border can all be set in a shorthand.
```
border:3px solid green;
```

- **Margin** - Margin sits outside the border of a box. we can adjust these to create a gap between the borders of adjacent elements. Margin is commonly set in pixels, but it can be designated using ems or a percentage *(this will be a percentage of the browser window)* If two margins overlap the margin with the largest width will be shown and the smaller will be disregarded. If a width has been assigned to the box, any margin will be added around that box. Margins can be set with a single value, various values can be set for any of the 'trouble'*(TRBL)* directions: -top, -right, -bottom, -left, or the margin on top and bottom and left and right can be set in a shorthand.
```
margin:5px 10px;
```
- **Padding** - Padding is the space between the border of the box and the content which it contains. Adding padding can increase readability of content. Again, commonly designated in pixels, but can be set with ems or percentages *(this will be a percentage of the browser window or a parent container if one exists)*. If a width has been assigned to the box, padding will be added to that width. Padding can be set with a single value, various values can be set for any of the 'trouble'*(TRBL)* directions: -top, -right, -bottom, -left, or the padding on top and bottom and left and right can be set in a shorthand.
```
padding:6px 24px 12px 24px;
```

Padding and margins are helpful for adding "white space" between various items on the page.

### Centering
In order to center a box on the page or within the element in which it sits, we must first set a width for the box and then set the `margin-left` and `margin-right` properties to *auto*.

**IE6 Box Model**

Reference page 316 of the book to read about quirks concerning boxes, margins and padding...

### Display
The display property allows us to change inline elements into block elements and vice versa. It also allows us to hide an element from the page. The possible values are:
- `inline` - causes a block-level element to behave like an inline element
- `block` - causes an inline element to behave like a block-level element
- `inline-block` - causes a block-level element to flow like an inline element while retaining other features of a block-level element
- `none` - hides the element from the page as though it isn't there

### Visibility
The visibility property allows us to hide boxes from users while leaving a space where the element would have been displayed. The values are:
- `hidden` - hides the element
- `visible` - shows the element

## CSS3 borer-image, box-shadow and border-radius

**border-image**

Takes a background image and slices it into nine-pieces and then applies those pieces to the border of any box. The four corner pieces are always positioned at the corners of the box, but we have an option on whether the side pieces are stretched or repeated. The property requires the following pieces of information:
1. The URL of the image
1. Where to slice the image
1. What to do with the straight edges (`stretch` , `repeat` , `round`)

The box must also have a border width for the image to be shown.

**box-shadow**

Allows us to add a drop shadow around the box. The information we can include is:
`Horizontal Offset`
`Vertical Offset`
`Blur Distance`
`Spread of Shadow`
`Color`

If the **inset** keyword is inserted before the values, they will create an 'inner' shadow.

**border-radius**

Used to create rounded corners on any box. The value indicates the number of pixels the radius of the rounded corner should be. This can also be designated as a percentage of the height/width of the box as well. One value can be given and applied to all of the corners of the box, or different corners can be targeted individually with varying values. For instance:
```CSS
article {
    border-top-left:20px;
    border-bottom-right:10px;
}
```




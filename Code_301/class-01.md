# SMACSS and Responsive Web Design

---

## Responsive Web Design

**\_\_\_\_** **\_ \_\_\_\_** is the practice 0f building a website suitable to work on every device and every screen size.

Responsive websites continually and fluidly change based on different factors, such as viewport width, while \***\*\_\_\_\_\*\*** websites are built to a group of preset factors.

**\_\_**, on the other hand, generally means to build a separate website commonly on a new domain solely for mobile users.

Currently, the most popular technique lies within responsive web design, favoring design that **\_\_\_\_** adapts to different browser and device viewports.

Responsive web design is broken down into three main components, including **flexible layouts**, **media queries**, and **flexible media**.

### Flexible Layouts

Flexible layouts is the practice of building the layout of a website with a flexible \_\_\_\_, capable of dynamically resizing to any width.

CSS3 introduced some new relative length units:

- `vw` - viewports width
- `vh` - viewports height
- `vmin` - minimum of the viewport's height and width
- `vmax` - maximum of the viewport's height and width

The formula for identifying the relative width of a an element is based on dividing the target width of an **\_\_\_\_** by the width of its parent **\_\_\_\_**.

Using the **\_\_** \_\_ formula, we can convert all fixed units of length to relative units, so that no matter how wide the parent container is the contained element will scale **\_\_**.

When the layout gets too small, or too large, text may become illegible and the layout may begin to break. In this event the flexible layout approach alone won't be enough, but **\_\_** **\_\_** can be used to help build a better experience.

### Media Queries

Two ways to use media queries are by importing a new style sheet using the **\_\_** rule or by using the **\_\_** rule inside of an existing style sheet, which is the generally recommended method.

Each media query may include a media type followed by one or more expressions. When a media feature and value allocate to \_**\_, the styles are applied. If the media feature and value allocate to \_\_\_\_** the styles are ignored.

#### Logical Operators in Media Queries

There are three different **\_\_** operators available for use within media queries: `and`, `not` and `only`. Using these we can build powerful expressions.

Using the `and` operator allows an extra condition to be added...

```CSS
@media all and (min-width: 800px) and  (max-width: 1024px) {...}
```

The `not` operator negates the query, specifying any query but the one identified.

```CSS
@media not screen and (color) {...}
```

The `only` operator is a new operator that isn't recognized by HTML4. Styles including this operator are hidden from devices/browsers that do not support media queries

```CSS
@media only screen and (orientation: portrait) {...}
```

#### Media Features in Media Queries

Media **\_\_\_\_** identify what attributes or properties will be targeted within the media query expression.

One of the most common media features revolves around determining a **\_\_** or **\_\_** for a device or browser viewport. Their values may be any length unit, relative or absolute.

In responsive design, `min-width` and `max-width` are the most commonly used features. They help build **\_\_\_\_** websites on desktops and **\_\_** **\_\_** equally.

#### Orientation & Aspect Ratio

The `orientation` media feature determines if a device is in the \_\_\_\_ mode _(the display is wider than taller)_ or the \_\_\_\_ mode _(where the display is taller than wider)_. This media feature plays a large part with mobile devices.

The \_\_\_\_-\_\_\_\_ feature consists of two positive integers separated by a forward slash. The first identifies the \_\_\_\_ in pixels and the second identifies the **\_\_\_\_** in pixels.

```CSS
@media all and (min-device-aspect-ratio: 16/9) {...}
```

#### Other Media Features

Other media features include:

- `pixel-ratio` media features
- `resolution` media features
- `color`
- `monochrome`
- `color-index`
- `grid`
- `scan`

Writing media query breakpoints around common viewport sizes such as 320px, 480px, 768px, 1024px and so forth is a \_\_\_\_ idea. New devices and resolutions are being introduced all the time.

#### Mobile First

The **\_\_** \_\_\_\_ approach includes using styles targeted at smaller viewports as the default styles for a website, then use media queries to add style as the viewport grows. This saves bandwidth.

Downloading unnecessary media assets like shadows, gradients, transforms and animations in mobile styles can **\_** loading and \_\_\_\_ battery life. Media queries can be used to stop these.

#### Viewport

Using the `viewport` meta tag with either the height or width values will define the height or width of the viewport. For best results, it is recommended that we use the `device-height` and `device-width` values to inherit the device's **\_\_** and **\_\_**.

```HTML
<meta name="viewport" content="width=device-width">
```

The **\_\_**`-scale` and **\_\_**`-scale` values determine how small and how large a viewport may be scaled.

Turning off the ability to scale a website is a \_\_\_\_ idea.

The `viewport` meta tag will accept **\_\_\_\_** values as well as **\_\_\_\_** values, allowing several properties to be set at once.

### Flexible Media

Images, videos and other media types need to be **\_\_\_\_**, changing their size as the size of the viewport changes.

A quick way to make media scalable is by using the **\_\_** property with a value of 100%, ensuring that as the viewport gets smaller, any media will scale down according to its container's width.

The `max-width` property doesn’t work well for all instances of media, specifically around **\_\_\_\_** and embedded media. _(see [Responsive Web Design](https://learn.shayhowe.com/advanced-html-css/responsive-web-design/) for a work around)_.

## Floats

**Float** is a CSS positioning **\_\_\_\_**.

Floated elements _remain a part of the flow of the web page_. Which is distinctly different from page elements that us **\_\_\_\_** positioning.

There are four valid values for the float property:

- **Left** floats elements left
- **Right** floats elements right
- **None** _default_ ensures the element will not float
- **\_\_\_\_** element will assume the float value from its parent element

Floats can be used to create entire web layouts, but stronger tools are **\_\_\_\_** and \_\_\_\_.

**\_\_\_** are still useful because they still have abilities unique to them.

Float's sister property is **\_\_\_\_**.

An element that has the `clear` property on it will not move up adjacent to the **\_\_\_** element, but will move itself down below it.

`clear` has four valid values:

- **\_\_** is most commonly used and clears floats coming from either direction
- **Left** clears floats to the left
- **Right** clears floats to the right
- **None** which is the default

If a parent element contains nothing but floated elements, the **\_\_\_\_** of it would literally collapse to nothing.

Collapsing almost always needs to be dealt withto prevent strange layout problems. We fix it by clearing the float **\_\_\_\_** the floated elements in the container but **\_\_\_\_** the close of the container.

### Techniques for Clearing Floats

**The Empty Div Method** is quite literally an empty div

```HTML
<div style="clear: both;"></div>
```

**The Overflow Method** relies on setting the overflow CSS property on a parent element causing the parent to expand to contain the floats if set to **\_\_** or **\_\_**.

**The Easy Clearing Method** uses a clever CSS pseudo selector (`:after`) to clear floats. Instead of setting overflow on the parent, we apply an additional class like "clearfix" to it and then apply CSS:

```CSS
.clearfix:after {
   content: ".";
   visibility: hidden;
   display: block;
   height: 0;
   clear: both;
}
```

**\_\_\_\_** scenarios call for **\_\_\_\_** float clearing methods.

### Problems with Floats

- **Pushdown** is a symptom of an element inside a floated item being wider than the float itself.
  - _Quick fix:_ use `overflow: hidden;` to cut off excess
- *Double Margin Bug\*\* if margin is applied in the same direction as the float it will *double the margin\*.
  - _Quick fix:_ set `display: inline;` on the float
- **the 3px Jog** is when text that is up next to a floated element is mysteriously kicked away by 3px.
  - _Quick fix:_ set a width or height on the affect text
- **Bottom Margin Bug** (IE7) is when if a floated parent has floated children inside, bottom margin on those children is ignored by the parent.
  - _Quick fix:_ using bottom padding on the parent instead

### Alternatives

If you need text wrapping around images, there really aren't any alternatives for **\_\_\_\_**.

[Back to Main](../README.md)

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

#### Orientation

[Back to Main](../README.md)

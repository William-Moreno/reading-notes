# Assorted Topics

---

## Images

Controlling the size and alignment of our images using CSS keeps the rules that affect the presentation of our page in the CSS and out of the HTML markup. We are also able to achieve many interesting effects using background images. Specifying image sizes helps pages to load more smoothly as well. This is because the HTML and CSS code will often load before the images but because we have already specified the dimensions of the space needed for the image, the page can continue to load without having to wait for each image to be rendered before proceeding.

### Sizes

Using consistently sized images across the site means that we can use CSS to control the dimensions of the images by setting image dimensions for two or three different sizes and assigning them to classes in CSS. THen we simply need to give each `<img>` tag in HTML whichever class attribute matched the size we wish for it to be.

### Alignment

The `float` property can be used to move an element to the left or the right of its containing blockallowing text to flow around it. `float` is often used to align images. There are two common ways this is done:

1. The `float` property is added to the class that was created to represent the size of the image.
1. _New_ classes are created with names such as "align-left" or "align-right" to align the images to the left or right of the page. These classes are used _in addition to_ classes that indicate the size of the image. It is also common to add margin to the image to ensure that the text does not touch their edges.

### Centering

Images are inline elements by default. To center them, we should turn them into block-level components using the `display: block;` CSS property. Then there are two common ways to center the image horizontally:

1. On the containing element, we can use the `text-align` property with a value of `center`.
1. On the image itself, we can use the `margin` property to set the values for the left and right margins to `auto`.

## Background Images

The `background-image` property allows us to place an image behind any HTML element, from the entire page, to a spcific element like a `<div>` or a `<button>`. We specify the path to our desired image as such: `background-image: url(path to image)`.

### Repeating Images and Positioning

By default, the background image will repeat to fill its entire container, but this can be altered by using the `background-repeat` property along with one of its four settings:

- `repeat` - the background image is repeated both horizontally and vertically. (if we do not specifically declare the `background-repeat` property, the image will display this way)
- `repeat-x` - the image is repeated horizontally only
- `repeat-y` - the image is repeated vertically only
- `no-repeat` - the image is shown only once

The `background-attachment` property can only have two values assigned to it. Use `scroll` when we want the image to scroll up and down the page when the user scrolls. When we use `fixed` to command the image to stay location in the same position on the page regardless of scrolling.

When an image is not being repeated, it can be positioned using the `background-position` property. The property typically has a pair of values: horizontal and vertical. These values can be represented (left/center/right) (top/center/bottom), or even measured in pixels or percentages from the top, left corner of the screen.

#### Shorthand

all of these properties can be combined into a shorthand such as:

```CSS
body {
 background: #ffffff url("images/tulip.gif") no-repeat top right;
}
```

The properties must be listed in the specified order:

1. `background-color`
1. `background-image`
1. `background-repeat`
1. `background-attachment`
1. `background-position`

Any particular property value can be skipped if desired, but the order must be maintained.

### Image Rollovers & Sprites

It is possible to achieve a sort of background animation by using an image that is larger than the container of an element such as a button, that can only show part of that background at a time. Then setting the image to move by changing its position with the pseudo-classes `:hover` and `:active`.

### Gradients

Gradients can be achieved in CSS3 by using the `background-image` property. The syntax used is:

```CSS
background-image: linear-gradient (color1, color2);
```

#### Contrast

Contrast of most background images is high. If we wish to overlay text on the image, the images must be low contrast in order for the text to be legible. Placing a semi-transparent background color for our text element can work as an overlay for the background image and make the text easier to read.

## Practical Information

The concepts herein touch on briefly on:

- The basics of search engine optimization
- Using analytics to understand how people are using your site after it has launched
- Putting our site on the web

### Search Engine Optimization (SEO)

Search engine optimization is the practice of trying to help your site appear nearer the topof search engine results when people look for the topics that your website covers. The practice is split into two areas:

1. On-page Techniques
1. Off-page Techniques

#### On-page Techniques

These are methods we can use on our web pages to improve their rating in search engines. The main component of this is looking at keywords that poeple aree likely to enter into a search engine if they wanted to find our site, and including them in at least one of seven essential places:

1. Page Title
1. URL / Web Address
1. Headings
1. Text
1. Link Text
1. Image Alt Text
1. Page Descriptions
   - _The description also lives inside the `<head>` element and is specified using a `<meta>` tag. It should be a sentence that describes the content of the page._

Determining which keywords to use on our site can be one of the hardest tasks when we atart to think about **SEO**. Six steps that help us identify the correct keywords and phrases for our site are:

1. Brainstorm
1. Organize
1. Research
1. Compare
1. Refine
1. Map

### Analytics

Analytics tools such as _Google Analytics_ allow us to see how many people visit our site, how they find it, and what they do when they get there. This service requires signing up for an account at [www.google.com/analytics](www.google.com/analytics) Then we must insert the provided tracking code into the HTML for the site we wish to track. It should appear just before the closing `</head>` tag. The code does not alter the appearance of our web page.

Google then provides a web-based interface that allows us to see how visitors use our site.

The Overview page gives us a snapshot of the key information such as:

- visits
- unique visits
- page views
- pages per visit
- average time on site

and much more information on differing tabs/links

### Domain Names & Hosting

To put our site on the web, we will need to obtain a domain name and web hosting.

FTP programs allow us to transfer files from our local computer to our web server.

## Video & Audio APIs

[Back to Main](README.md)

# HTML Images, CSS Color & Text

---

## Images

There are several things to consider when selecting and preparing images for our site. Things to consider are:

- Which image format to use
- What size to show an image at
- How to optimize an image for use on the web to make pages load faster

_CSS can also be used to include images on our pages using the `background-image:` property._

### Choosing Images and Storing Them on Our Site

Remember that all images are subject to copyright. We can get into trouble for simply taking photos from another website. If our page will show several related images, putting them all on simple, consistent backgrounds will help them look better as a group.

#### Images Should...

- Be relevant
- Convey information
- Convey the right mood
- Be instantly recognizable
- Fit the color palette

When building our site from scratch, it is good practice to create an **images** folder for all of the images the site will use. The folder could be subdivided into folders for images pertaining to specific pages or aspects of the site for better organization.

### Adding Images

We use an `<img>` tag in our HTML page to add an image. This is an empty element that does not require a closing tag. Three common attributes for this tag are `src` which is is where we insert the URL for the image, `alt` which provides a text description of the image _(useful if you are unable to see the image)_ and `title` to provide addition information about the picture that most browsers display when the user hovers over the image.

We can also set the height and/or width of the image using the `height` and `width` attributes. The numeric values assigned in these attributes are measures in pixels. However, better practice is to use CSS to designate dimensions of rendered images.

### Placing Images in Our Code

Where we place an image in our code will affect how it is displayed. Three examples are:

- **Before a Paragraph** - The paragraph will start on a new line after the image
- **Inside the Start of a Paragraph** - The first row of text aligns with the bottom of the image
- **In the Middle of a Paragraph** - The image is placed between the words of the paragrph that it appears in

### Three Rules for Creating Images

1. Save images in the right format _(jpeg, gir or png)_
1. Save images at the right size _(the size we intend to display it at)_
1. Measure images in pixels

### Tools to Edit & Save Images

There are several tools we can use to edit and save images for use. The most popular tool amongst professionals is **Adobe Photoshop**. However, there are other alternatives such as:

- Photoshop Elements
- Adobe Fireworks
- Pixelmator
- PaintShop Pro
- Paint.net
- _A number of online editors_

### Formats & Dimensions

WHen our image has many different colors, we should use a jpeg format. If the image has few colors or large areas of the same color, we should use gif or png formats.

Images should be saved at the same width and height that we want them to appear on the web page. We can _reduce_ the size of our image to create a smaller version of the image which is quicker to download. We can't _increase_ the size of our image significantly without making it look blurry or blocky. While we can _alter_ the shape of an image, only some images can be cropped and still make sense _(where at all possible, source images that are the correct shape. Don't crop)_.

#### Vector Images

Vector images are different from bitmap images and are resolution independent. They are commonly created in programs like Adobe Illustrator and are often employed for logos, diagrams and illustrations. **Scalable Vector Graphics _(SVG)_** are a relatively new format and their use is not yet widespread.

### Transparency

Creating an image that is partially transparent for the web involves selecting either _(transparent)_ gif or png. The png format offers more options for manipulation later including drop shadows...

### Figure and Figure Caption

HTML5 has introduced the `<figure>` element to contain images and any captions we wish to associate with them. Captions for he image(s) are added with the new `<figcaption>` tag.

## CSS Colors

### Colors

COlor not only brings our site to life, but also helps convey the mood and evokes reactions. When selecting colors for an element, they can be specified in several ways. However, the three most common are:

- **RGB** - Red, green and blue values ranging from 0 to 255.
- **Hex Codes** - A \# followed by a 6-digit code.
- **Color Names** - One of 147 preset colors recognized by browsers.

Colors can be apply to different things.

The `color` property sets the color of foreground items such as text.
The `background-color` property sets the color of the background of a particular element.

### Contrast

It is important to select text and background colors that provide enough contrast to be legible.

- **low contrast** - harder to read, particularly for the visually impaired or color blind
- **high contrast** - easier to read, but if there is a lot of text to be read, it can make it harder too
- **medium contrast** - improves readability for longer spans of text

### Opacity

Using color indicators like `rgba` or `hsla`, allows you to specify the opacity of a color. The "a" position is a value between 0.0 and 1.0 that represents a percentage of transparency. Some browsers may not support opacity so it is good practice to create an alternate backup CSS rule above the rule that those browsers can use.

## CSS Text

The properties that allow us to control the appearance of text can be divided into two groups:

1. Those that directly affect the font and its appearance, including:
   - typface
   - regular, **bold** or _italic_
   - size
1. Those that would have the same effect on text no matter which font we are using, including:
   - color
   - spacing
     - between words
     - between letters

### Typeface, Weight, Style . . .

When choosing a typeface for our site, it is important to understand that a browser will usually only display it if it is installed on the user's computer. Three more common types are:

- **Serif** - letters with extra details on them traditionally used in print.
- **Sand-Serif** - letters have straight ends and a much cleaner design. On a screen, if the text is small, sans-serif can be easier to read.
- **Monospace** - every letter is the same width. Commonly used for code because they align nicely, making the text easier to follow.

`font-family` is the property which specifcies typeface

`font-size` is a property that allows us to specify a size for the font in pixels, percentages or ems _(equivalent to the width of a letter "M")_

- the default size of text in a browser is 16 pixels
- When designing, we should choose text heights from the scale developed in the 1500s and common to most programs like Word, Photoshop and InDesign.

`font-weight` commonly takes one of two values, _normal_ or _bold_

`font-style` used to create italic text. THere are three possible values: _normal_, _italic_ or _oblique_

`text-transform` is used to change the case of text with values like: _uppercase_, _lowercase_ and _capitalize_

`text-decoration` can be used to underline, overline or strikethrough text, etc.

`line-height`, `letter-spacing` and `word-spacing` are all properties which allow us to control the amount ospace between letters, words and lines of text

`text-align` can alter alignment of the text to left, center, right or justified

`text-indent` is the property which we can use to indent the first line of text within an element

#### Pseudo Elements

Technically these are not properties. They are more like selector extensions. They can be added to the end of selectors to designate specific parts of a word or text to modify or to respond to users.

- `:first-letter`
- `:first-line`
- `:link`
- `:visited`
- `:hover`
- `:active`
- `:focus`

### Further Selectors in CSS

| **Selector**  | **Meaning**                                                                                | **Example**       |
| ------------- | ------------------------------------------------------------------------------------------ | ----------------- |
| **Existence** | [ ] _Matches a specific attribute regardless of value_                                     | `p[class]`        |
| **Equality**  | [=] _Matches a specific attribute with a specific value_                                   | `p[class="dog"]`  |
| **Space**     | [~=] _Matches a specific attribute whose value appears in a space-separated list of words_ | `p[class~="dog"]` |
| **Prefix**    | [^=] _Matches a specific attribute whose value begins with a specified string_             | `p[attr^="d"]`    |
| **Substring** | [*=] _Matches a spcific attribute whose value contains a specific substring_               | `p[attr*="do"]`   |
| **Suffix**    | [$=] _Matches a specific attribute whose value ends with a specific string_                | `p[attr$="g"]`    |

[Back to Main](README.md)

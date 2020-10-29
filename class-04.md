# HTML Links, CSS Layout and JS Functions

---

## Writing Links

Links are the defining feature of the web. They allow us to move from one web page to another - the definition of browsing or surfing.

Links will commonly take us:

- from one website to another
- from one page to another on the same website
- from one part of a web page to another part
- to a pre-addressed email in our mail program
- a page in a new browser window

Links are created using the `<a>` element. Users can click on anything between the opening `<a>` tag and the closing `</a>` tag in order to activate the link. We specify the destination we want to link to using the `href` attribute. By default, browsers show links in blue with an underline.

```HTML
<a href="http://www.imdb.com">IMDB</a>
```

Link text _(the text between the `<a></a>` tags)_ should be clear and specific and should explain where visitors will be taken if they click on it.

### Linking to Other Sites

When we link to a different website, we insert the full web address, or **absolute** URL in the `href` attribute. URL stands for Uniform Resource Locator and every web page has its own. If no specific path follows the domain name, the site will display the homepage.

### Linking to Other Pages on the Same Site

When we link to other pages within the same site, we can omit the domain name and use a shorthand known as a **relative** URL in the `href` attribute. Pages in the same folder as the current page need only be specified by file name. When the target page is in a different folder of the directory the relative URL will be slightly more complex.

On larger sites, we should organize our code by placing the pages for different sections into new directories. The directory structure for a website resembles and uses the terminology of a family tree. The top level is known as the **root** folder. The root contains all of the files and folders (which in turn contain other files) for the website. Always in the root, and often in the children folders, there will be an index.html file that is the homepage for the site or that section of the site. Web servers are commonly set up to return the index.html file if no other file is specified. When we understand the structure of our directory and the relationships of the folders and files within, we can use the correct shorthand to navigate with links.

**Navagating Site Pages with Relative URLs**

| **Relative Link Type** | **Shorthand**                                                                                                      |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------ |
| Same Folder            | When linking to a file in the same folder, just use the file name.                                                 |
| Child Folder           | For a child folder, use the name of the child folder, followed by a foward slash, then the file name.              |
| Grandchild Folder      | Use the name of the child folder, forward slash, name of the grandchild folder, forward slash, then the file name. |
| Parent Folder          | Use `../` to indicate the folder above the current one, then the file name.                                        |
| Grandparent Folder     | Use `../../` to indicate the folder above the folder above the current one and then the file name.                 |

### Email Links

To create a link that opens the user's email program and addresses an email to a specified recipient, we insert `mailto:specifiedRecipient@email.email` into the `href` attribute of our `<a>` tag.

### Opening Links in a New Window

To open a link in a new window, we use the `target` attribute in our `<a>` tag, with a value of `_blank`. Generally, we should avoid opening links in new windows, but if we do, it is good practice to inform users that the link will open a new window before they click on it.

### Linking to Specific Parts of the Same Page

To link to specific parts of our page we assign id attributes to the desired destination tags. Then in the `href` attribute of our `<a>` tag we simply insert `#id-assigned`. The link will now navigate to the element with the specified id attribute. This will work to reference specifically identified elements of other pages as long as `#id-assigned` is added to the end of whatever URL we place in the `href` attribute.

## CSS Layouts

CSS treats each HTML element as being in either a **block-level** box or an **inline** box. Block-level elements start on a new line and inline elements flow in between surrounding text. If a block-level element sits inside another block-level element, the outer element is known as the **containing** or **parent** element.

### Position

Using the `position:` property, CSS allows us to control the layout of a page in the following ways: normal flow, relative positioning, absolute and fixed.

- **Normal Flow** - _(the default behavior)_ Every block-level element will appear on a new line, even if there is enough space for two elements to sit side-by-side.
- **Relative Positioning** - Moves an element in relation to where is would normally have been positioned.
- **Absolute Positioning** - Takes an element out of normal flow and positions it in relation to its containing element. It will no longer affect the positioning of any surrounding elements.
- **Fixed Positioning** - This is a form of absolute positioning that takes an element out of normal flow and positions it in relation to the browser window as opposed to its containing element. Further, these elements will persist in their locations when the user scrolls the page.

## JavaScript Functions

**Functions** are a series of statements grouped together into a single block that instruct the browser to perform a certain task. A function must be **declared** or defined. having declared a function we can then **call** that function any time we want the computer to perform that task.

Declaration of a function requires the function keyword, a function name (also called an **identifier**) we designate, possibly a list of parameters the function requires and a series of one or more statements located inside curly brackets to perform the given task. An example might be:

```JavaScript
function sayHello() {
 document.write('Hello!');
}
```

- `sayHello` is the function's name
- this function requires no parameters
- `document.write('Hello!);` is the statement the function will execute

If a function requires specific information in order to perform its task, there will be a list of **parameters** inside the () following the function's name. For instance, in the case of `getArea(width,height)`, the getArea function would need the values for width and height supplied to it in order to execute its task. When we supply this information is is known as passing **arguments** into the function. In the case above, we would pass in values for _width_ and _height_.

Finally, by including the `return` keword in the statements of the function we can have the called function return a value to the code that _called_ the function and then exit the function, ignoring any subsequent statements remaining below it in the block. Functions can also return more than one value using an **array**.

[Back to Main](README.md)

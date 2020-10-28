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

**Linking to Other Sites**

When we link to a different website, we insert the full web address, or **absolute** URL in the `href` attribute. URL stands for Uniform Resource Locator and every web page has its own. If no specific path follows the domain name, the site will display the homepage.

**Linking to Other Pages on the Same Site**

When we link to other pages within the same site, we can omit the domain name and use a shorthand known as a **relative** URL in the `href` attribute. Pages in the same folder as the current page need only be specified by file name. When the target page is in a different folder of the directory the relative URL will be slightly more complex.

On larger sites, we should organize our code by placing the pages for different sections into new directories. The directory structure for a website resembles and uses the terminology of a family tree. The top level is known as the **root** folder. The root contains all of the files and folders (which in turn contain other files) for the website. Always in the root, and often in the children folders, there will be an index.html file that is the homepage for the site or that section of the site. Web servers are commonly set up to return the index.html file if no other file is specified. When we understand the structure of our directory and the relationships of the folders and files within, we can use the correct shorthand to navigate with links.

**Navagating Site Pages with Relative URLs**
| **Relative Link Type** | **Shorthand** |
| --- | --- |
| Same Folder | When linking to a file in the same folder, just use the file name. |
| Child Folder | For a child folder, use the name of the child folder, followed by a foward slash, then the file name. |
Grandchild Folder | Use the name of the child folder, forward slash, name of the grandchild folder, forward slash, then the file name. |
| Parent Folder | Use `../` to indicate the folder above the current one, then the file name. |
| Grandparent Folder | Use `../../` to indicate the folder above the folder above the current one and then the file name. |

**Email Links**

To create a link that opens the user's email program and addresses an email to a specified recipient, we insert `mailto:specifiedRecipient@email.email` into the `href` attribute of our `<a>` tag.

**Opening Links in a New Window**

To open a link in a new window, we use the `target` attribute in our `<a>` tag, with a value of `_blank`. Generally, we should avoid opening links in new windows, but if we do, it is good practice to inform users that the link will open a new window before they click on it.

**Linking to Specific Parts of the Same Page**

To link to specific parts of our page we assign id attributes to the desired destination tags. Then in the `href` attribute of our `<a>` tag we simply insert `#id-assigned`. The link will now navigate to the element with the specified id attribute. This will work to reference specifically identified elements of other pages as long as `#id-assigned` is added to the end of whatever URL we place in the `href` attribute.

[Back to Main](README.md)
